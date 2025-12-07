---
sidebar_position: 3
---

# Chapter 3: Running Basic AI Examples in NVIDIA Isaac Sim

With NVIDIA Isaac Sim successfully installed and configured, it's time to experience the application of AI within this powerful simulation environment. This chapter will guide you through loading sample robots, understanding pre-configured AI tasks, and observing autonomous behaviors.

## 1. Navigating the Isaac Sim Interface

Before running examples, familiarize yourself with key areas of the Isaac Sim interface:

-   **Viewport**: The main 3D view where you interact with your virtual environment.
-   **Stage**: Located on the left, this panel lists all the objects and assets currently in your scene (similar to a Unity Hierarchy).
-   **Property Window**: Located on the right, this panel shows the properties of selected objects, allowing you to modify their parameters.
-   **Content Browser**: Typically at the bottom, for accessing various 3D models, environments, and extensions.

## 2. Loading a Sample Robot and Environment

Isaac Sim comes with a rich set of examples and pre-built robots. We'll start by loading a simple navigation example.

1.  **Open a Sample Scene**:
    -   In the Isaac Sim UI, go to `File > Open`.
    -   Navigate to `isaac_sim/standalone_examples/api/omni.isaac.kit/python_examples/hello_world.py` (or similar path for basic examples).
    -   Alternatively, explore the `Isaac Examples` panel usually available from `Window > Isaac Examples`. Look for navigation or manipulation demos.

2.  **Understand the Scene**:
    -   Once loaded, the scene will typically include a robot (e.g., a simple mobile robot like a differential drive bot) and an environment (e.g., a maze or a simple room).
    -   Observe how the robot model is structured in the Stage panel (often a USD file).

## 3. Executing Basic AI-Driven Behaviors

Many Isaac Sim examples are driven by Python scripts that define the AI logic and robot behavior. These scripts interact with the simulation engine to control the robot.

1.  **Launch the Script**:
    -   If you opened a `.py` file, it might automatically run the simulation or provide instructions to do so.
    -   For examples from `Isaac Examples` panel, there's usually a "Run" button associated with each example.

2.  **Observe Autonomous Behavior**:
    -   As the simulation runs, observe the robot's behavior. For a navigation example, you might see the robot moving autonomously, avoiding obstacles, or reaching target points.
    -   The console output (often at the bottom of the Isaac Sim window) will usually provide logging information about the AI's decisions or sensor readings.

## 4. Understanding the Underlying AI Logic (High-Level)

While the full details of the AI algorithms are beyond this introductory chapter, you can get a high-level understanding by:

-   **Reviewing the Python Script**: If the example is driven by a Python script, briefly examine the code. Look for sections where:
    -   Sensor data is read (e.g., lidar, camera).
    -   AI models are loaded or executed.
    -   Control commands are sent to the robot (e.g., linear and angular velocities).
-   **Identifying Key ROS 2 Connections**: If the example uses the ROS 2 bridge, identify the ROS 2 topics being published (e.g., sensor data) and subscribed to (e.g., velocity commands).

## 5. Experimenting (Optional)

Many examples allow for basic experimentation:

-   **Modify Robot Properties**: Pause the simulation, select the robot in the Stage panel, and try modifying some of its physical properties (e.g., mass, friction) in the Property Window.
-   **Change Environment**: Add or remove obstacles, or change the lighting.
-   **Adjust AI Parameters**: If the script exposes any parameters (e.g., navigation goal, obstacle avoidance threshold), try adjusting them and re-running the simulation to see the effect.

By running these basic AI examples, you gain a tangible understanding of how theoretical AI concepts translate into practical robot behaviors within a high-fidelity simulation environment. In the next chapter, we'll explore how Isaac Sim can be used to generate synthetic data for training these AI models.
