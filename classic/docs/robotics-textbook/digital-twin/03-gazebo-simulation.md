---
sidebar_position: 3
---

# Chapter 3: Running Basic Gazebo Simulations

With Gazebo installed and integrated with ROS 2, it's time to launch our first simulation and interact with a virtual robot. This chapter will guide you through loading predefined robot models and controlling them within the Gazebo environment.

## 1. Launching a Gazebo World

Gazebo allows you to load various "worlds" – environments with different terrains, obstacles, and lighting conditions. We'll start with a simple empty world.

```bash
# Ensure your ROS 2 environment is sourced
source /opt/ros/humble/setup.bash

# Launch an empty Gazebo world
ros2 launch gazebo_ros gazebo.launch.py empty_world:=true
```

This command will open the Gazebo simulator with an empty 3D environment. You can pan, zoom, and rotate the view to get familiar with the interface.

## 2. Spawning a Robot Model

Now, let's add a robot to our empty world. We'll use a `turtlebot3_burger` model, a popular research and education robot. First, ensure you have the necessary TurtleBot3 ROS 2 packages installed:

```bash
sudo apt update
sudo apt install ros-humble-turtlebot3-msgs ros-humble-turtlebot3-gazebo
```

Now, you can spawn the TurtleBot3 Burger in your Gazebo world:

```bash
# In a new terminal (ensure ROS 2 is sourced)
export TURTLEBOT3_MODEL=burger
ros2 launch turtlebot3_gazebo robot_state_publisher.launch.py
ros2 run gazebo_ros spawn_entity.py -entity turtlebot3_burger -topic robot_description -x 0.0 -y 0.0 -z 0.0
```

You should now see the TurtleBot3 Burger robot appear in your Gazebo simulation.

## 3. Interacting with the Robot (ROS 2 Control)

We can control the robot by publishing messages to its command topics. For the TurtleBot3, we can send twist messages (linear and angular velocities) to the `/cmd_vel` topic.

#### Sending Commands from the Command Line

You can send simple commands directly from the terminal using `ros2 topic pub`:

```bash
# In another new terminal (ensure ROS 2 is sourced)
ros2 topic pub /cmd_vel geometry_msgs/msg/Twist "{linear: {x: 0.2, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.0}}" -1
```

This command will make the robot move forward at 0.2 m/s. The `-1` flag sends the message once and then exits. To make it move continuously, you can omit the `-1` or publish a stream of messages.

#### Controlling with a Simple Python Node

Let's create a Python node to send continuous velocity commands. Create a file `simple_mover.py` in your ROS 2 workspace (e.g., in a package named `my_gazebo_control`):

```python
import rclpy
from rclpy.node import Node
from geometry_msgs.msg import Twist

class SimpleMover(Node):
    def __init__(self):
        super().__init__('simple_mover')
        self.publisher_ = self.create_publisher(Twist, 'cmd_vel', 10)
        timer_period = 0.1  # seconds
        self.timer = self.create_timer(timer_period, self.timer_callback)
        self.linear_vel = 0.1
        self.angular_vel = 0.5

    def timer_callback(self):
        msg = Twist()
        msg.linear.x = self.linear_vel
        msg.angular.z = self.angular_vel
        self.publisher_.publish(msg)
        self.get_logger().info(f'Publishing: Linear.x={self.linear_vel}, Angular.z={self.angular_vel}')

def main(args=None):
    rclpy.init(args=args)
    simple_mover = SimpleMover()
    rclpy.spin(simple_mover)
    simple_mover.destroy_node()
    rclpy.shutdown()

if __name__ == '__main__':
    main()
```

Remember to add this script to your `setup.py` and rebuild your package. Then you can run it:

```bash
# Build your package (e.g., my_gazebo_control)
colcon build --packages-select my_gazebo_control

# Source the setup files
source install/setup.bash

# Run your simple mover node
ros2 run my_gazebo_control simple_mover
```

The robot in Gazebo should now start moving! You can adjust `linear_vel` and `angular_vel` in the Python script to change its behavior.

## 4. Visualizing Sensor Data (Optional)

Many simulated robots publish sensor data (e.g., laser scans, camera images) to ROS 2 topics. You can visualize this data using `rviz2`.

```bash
# In a new terminal (ensure ROS 2 is sourced)
rviz2
```

In `rviz2`, you can add various displays (e.g., `LaserScan`, `Image`) and subscribe to the relevant ROS 2 topics (e.g., `/scan`, `/camera/image_raw`) to see the robot's perception of its simulated environment.

By performing these steps, you have successfully launched a Gazebo simulation, spawned a robot, and controlled it using ROS 2. This hands-on experience forms the basis for more advanced digital twin applications.
