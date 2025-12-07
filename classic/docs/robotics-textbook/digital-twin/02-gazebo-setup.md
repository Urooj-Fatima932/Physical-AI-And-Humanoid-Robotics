---
sidebar_position: 2
---

# Chapter 2: Gazebo Simulator Setup and ROS 2 Integration

Gazebo is one of the most widely used open-source 3D robotics simulators. It allows you to accurately simulate complex robots in diverse environments, making it an indispensable tool for developing and testing robotics applications. This chapter will guide you through setting up Gazebo and integrating it with ROS 2.

## 1. Gazebo Installation

If you followed the Quickstart Guide, Gazebo was likely installed as part of your ROS 2 Humble setup. To verify, you can simply try to launch it:

```bash
gazebo --verbose
```

If Gazebo launches successfully, you are good to go. If not, or if you prefer a standalone installation, follow these steps:

```bash
# Add Gazebo repository
sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable `lsb_release -cs` main" > /etc/apt/sources.list.d/gazebo-stable.list'
wget https://packages.osrfoundation.org/gazebo.key -O - | sudo apt-key add -

# Update and install Gazebo (Gazebo 11 is the default for Ubuntu 22.04 LTS)
sudo apt update
sudo apt install gazebo11
sudo apt install libgazebo11-dev
```

## 2. ROS 2 - Gazebo Integration

To allow ROS 2 to communicate with Gazebo, you need a set of ROS 2 packages known as `ros_gz`. These packages provide bridges and plugins to facilitate the exchange of data and commands between ROS 2 and Gazebo.

### Install `ros_gz` Bridge

The `ros_gz` bridge allows you to connect ROS 2 topics to Gazebo topics, enabling your ROS 2 nodes to send commands to a simulated robot and receive sensor data from it.

```bash
sudo apt update
sudo apt install ros-humble-ros-gz
```

### Gazebo ROS 2 Control (Optional, but recommended)

For more advanced control of robots in Gazebo from ROS 2, especially when using `ros2_control`, you might need additional plugins. These are often included with robot-specific ROS 2 packages.

```bash
# Example: Install a common ROS 2 control package (if not already installed with ROS 2 desktop)
sudo apt install ros-humble-ros2-control ros-humble-ros2-controllers
```

## 3. Verifying Your Setup

To ensure Gazebo and its ROS 2 integration are working correctly, you can try launching a basic Gazebo world with a ROS 2 compatible robot.

### Example: Launching a Diff-Drive Robot in Gazebo

1.  **Create a simple ROS 2 package for your robot (if you don't have one)**:
    Let's assume you have a package named `my_robot_description` that contains a URDF/XACRO description of your robot and a launch file to spawn it in Gazebo.

2.  **Launch Gazebo with a robot**:
    A common way to launch a robot in Gazebo from ROS 2 is using a launch file. This launch file typically starts Gazebo and then spawns your robot model.

    ```bash
    # Example: This command would vary based on your robot's launch files
    ros2 launch my_robot_bringup my_robot.launch.py
    ```

    (Replace `my_robot_bringup` and `my_robot.launch.py` with your actual package and launch file names.)

    If you have a simple URDF model (e.g., from an existing tutorial), you can also spawn it directly using Gazebo's command-line tools if you have the model's path.

By successfully installing Gazebo and its ROS 2 bridge, you've established a powerful virtual environment for developing and testing your robotics applications. In the next chapter, we'll dive into running simulations and interacting with robots within Gazebo.
