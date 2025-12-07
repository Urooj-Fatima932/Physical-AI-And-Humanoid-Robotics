---
sidebar_position: 4
---

# Chapter 4: Unity for Robotics Simulation: Setup and Basics

While Gazebo is a powerful open-source simulator deeply integrated with ROS 2, Unity offers an alternative platform known for its high-fidelity graphics, advanced physics engine, and extensive asset store. Unity, traditionally a game development engine, is increasingly being adopted for robotics simulation due to its visual realism and robust development environment. This chapter will guide you through setting up Unity for robotics and understanding its basic concepts.

## 1. Unity Hub and Unity Editor Installation

If you followed the Quickstart Guide, you should already have Unity Hub and a Unity Editor installed.

-   **Unity Hub**: This is a management tool that helps you manage different versions of the Unity Editor and your Unity projects.
-   **Unity Editor**: This is the actual development environment where you build and simulate your robotics projects.

Ensure you have a recent LTS (Long Term Support) version of Unity Editor installed (e.g., 2022.3.x LTS).

## 2. Creating a New Unity Project for Robotics

1.  **Open Unity Hub**: Launch Unity Hub.
2.  **New Project**: Click on "New Project" (or "New" in older versions).
3.  **Template Selection**: Select a 3D template, typically the "3D Core" or "3D (URP)" template for Universal Render Pipeline if you plan for more advanced graphics. For basic robotics simulation, "3D Core" is sufficient.
4.  **Project Settings**: Give your project a meaningful name (e.g., `RoboticsSimulation`) and choose a location on your disk.
5.  **Create Project**: Click "Create Project". Unity Editor will open and initialize your new project.

## 3. Importing 3D Robot Models

Unity projects are initially empty. To simulate robots, you need to import their 3D models. Robots are often described using formats like URDF (Unified Robot Description Format), which is common in ROS.

### Importing URDF Models

Unity has specific tools to import URDF models. The **Unity Robotics Hub** provides a URDF importer package.

1.  **Open Package Manager**: In the Unity Editor, go to `Window > Package Manager`.
2.  **Add Package from Git URL**: Click the `+` icon in the top-left corner of the Package Manager window, and select "Add package from git URL...".
3.  **Enter URL**: Enter the Git URL for the Unity-Robotics-URDF-Importer (e.g., `https://github.com/Unity-Technologies/Unity-Robotics-URDF-Importer.git`).
4.  **Install**: Click "Add". The package will be downloaded and installed into your project.

Once installed, you can import a URDF file:

1.  Go to `Robotics > URDF Importer > Import Robot From URDF`.
2.  Browse to your URDF file (e.g., `my_robot.urdf`) and select it.
3.  Configure import settings (e.g., physics, colliders) and click "Import".

Your robot model should now appear in your Unity project's `Assets` folder and can be dragged into your scene.

## 4. Understanding Unity's Physics Engine

Unity's built-in physics engine (PhysX) is crucial for realistic robot simulations.

-   **Rigidbodies**: Any object you want to be affected by physics (gravity, collisions, forces) must have a `Rigidbody` component attached. Your imported URDF robot will typically have Rigidbodies on its links.
-   **Colliders**: These define the shape of an object for physics interactions. Make sure your robot's links have appropriate colliders (e.g., Box Collider, Sphere Collider, Mesh Collider).
-   **Joints**: Unity provides various joint components (e.g., Hinge Joint, Configurable Joint) to simulate mechanical connections between rigidbodies, crucial for robot kinematics and dynamics. The URDF Importer typically sets these up for you.

You can press the "Play" button in the Unity Editor to start the simulation and observe how your robot behaves under gravity and other forces. This forms the foundation for building interactive and high-fidelity robotics simulations.
