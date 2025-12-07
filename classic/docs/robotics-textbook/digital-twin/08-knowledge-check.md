---
sidebar_position: 8
---

# Knowledge Check: The Digital Twin (Gazebo & Unity)

You've completed the Digital Twin module! Let's assess your understanding of digital twin concepts, Gazebo simulation, and Unity for robotics.

## Part 1: Multiple Choice Questions

Choose the best answer for each question.

### Question 1: What is the primary characteristic of a digital twin in robotics?
A) It is a static 3D model of a robot.
B) It is a virtual replica that dynamically reflects its physical counterpart.
C) It is a program that controls a physical robot.
D) It is a tool exclusively for rendering realistic robot visuals.

### Question 2: Which of the following is NOT a common benefit of using digital twins in robotics?
A) Reduced costs for prototyping.
B) Faster iteration in development.
C) Elimination of the need for physical robots.
D) Safe testing of dangerous scenarios.

### Question 3: Which simulator is widely known for its deep integration with ROS 2 and open-source nature?
A) Unity
B) Unreal Engine
C) Gazebo
D) Blender

### Question 4: What is the "reality gap" in Sim-to-Real transfer?
A) The difference in computational power between a simulator and a real robot.
B) The discrepancy between simulated and real-world physics, sensor data, and environment.
C) The time delay in transferring data from a simulator to a physical robot.
D) The ethical concerns arising from using simulations instead of real tests.

### Question 5: Which Unity component is crucial for objects to be affected by physics (e.g., gravity, collisions)?
A) Transform
B) Mesh Renderer
C) Rigidbody
D) Camera

## Part 2: Practical Exercises

### Exercise 1: Gazebo Robot Launch and Control

1.  **Launch a Gazebo world**: Start an empty Gazebo world (or a simple world from the `gazebo_ros_pkgs`).
    ```bash
    ros2 launch gazebo_ros gazebo.launch.py empty_world:=true
    ```
2.  **Spawn a robot**: Spawn a `turtlebot3_burger` robot model into the Gazebo world.
    ```bash
    export TURTLEBOT3_MODEL=burger
    ros2 launch turtlebot3_gazebo robot_state_publisher.launch.py
    ros2 run gazebo_ros spawn_entity.py -entity turtlebot3_burger -topic robot_description -x 0.0 -y 0.0 -z 0.0
    ```
3.  **Control the robot**: Using the `ros2 topic pub` command, make the TurtleBot3 in Gazebo move forward for 5 seconds and then rotate in place for 3 seconds.

### Exercise 2: Unity Project Setup and Model Import

1.  **Create a new Unity project**: Launch Unity Hub and create a new 3D Core project.
2.  **Import a URDF model**: Install the Unity Robotics URDF Importer package into your new project. Import a simple URDF file (you can find examples online or use one provided by the Unity Robotics Hub).
3.  **Place and Simulate**: Drag your imported robot model into the scene. Add a ground plane. Run the simulation and observe if the robot's physics (e.g., falling due to gravity) behave as expected.

## Answers to Multiple Choice Questions

1.  B) It is a virtual replica that dynamically reflects its physical counterpart.
2.  C) Elimination of the need for physical robots.
3.  C) Gazebo
4.  B) The discrepancy between simulated and real-world physics, sensor data, and environment.
5.  C) Rigidbody
