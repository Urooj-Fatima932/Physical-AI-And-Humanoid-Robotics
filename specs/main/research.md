# Research Findings

This document summarizes the findings for the "NEEDS CLARIFICATION" items identified in the implementation plan.

## 1. Python Version for ROS 2 Humble

- **Finding**: ROS 2 Humble Hawksbill requires Python 3.8 or later. Ubuntu 22.04 LTS, the target OS, ships with **Python 3.10**.
- **Decision**: The project will standardize on **Python 3.10**. All code examples and instructions will use the `python3` command.

## 2. ISO-Standard Robotics Terminology

- **Finding**: The primary standard is **ISO 8373:2021 Robotics — Vocabulary**.
- **Decision**: A subset of key terms from this standard will be compiled and used consistently. A glossary will be created in the textbook. Key terms to include are:
    - **Robot**: A programmed actuated mechanism with a degree of autonomy to perform locomotion, manipulation or positioning.
    - **Industrial Robot**: An automatically controlled, reprogrammable, multipurpose manipulator programmable in three or more axes.
    - **Service Robot**: A robot that performs useful tasks for humans or equipment, excluding industrial automation.
    - **Mobile Robot**: A robot able to travel under its own control.
    - **Collaborative Robot (Cobot)**: A robot designed for direct interaction with a human within a shared space.
    - **End-effector**: The device at the end of a robotic arm, designed to interact with the environment.
    - **Actuator**: A component of a machine that is responsible for moving and controlling a mechanism or system.
    - **Kinematics**: The study of motion of points, bodies, and systems of bodies without considering the forces that cause them to move.
    - **VSLAM (Visual Simultaneous Localization and Mapping)**: A technique used by robots to build a map of an unknown environment while simultaneously keeping track of their location within it, using visual input.

## 3. Advanced Docusaurus Components

- **Finding**: Docusaurus offers many features to enhance educational content.
- **Decision**: The following components will be considered for implementation to improve the textbook's interactivity and clarity:
    - **Interactive Code Sandboxes**: Using `docusaurus-theme-live-codeblock` or a similar tool to allow students to run code in the browser.
    - **Custom Admonitions**: Creating custom blocks for "Exercise", "Learning Objective", and "Key Concept".
    - **Glossary and Tooltips**: Implementing a glossary page and potentially creating a custom React component to show term definitions on hover.
    - **Math Equations**: Integrating KaTeX for rendering mathematical formulas.
    - **Diagrams as Code**: Using Mermaid.js for creating diagrams from text to explain architectures and workflows.

## 4. Hardware-Specific Examples (Jetson Orin & RealSense)

- **Finding**: The NVIDIA Jetson Orin with JetPack 6 (Ubuntu 22.04) and ROS 2 Humble is a well-supported platform for the Intel RealSense D400 series cameras.
- **Decision**: The textbook will include a dedicated section in the `quickstart.md` and relevant chapters with instructions and examples for this hardware combination. Key points to cover:
    - **Setup**: Flashing JetPack 6, installing `librealsense2` SDK with patched kernel modules, and installing the `realsense2_camera` ROS 2 wrapper.
    - **Verification**: Using `realsense-viewer` to confirm camera operation and `rviz2` to visualize the data streams (color, depth, point cloud) from the ROS 2 topics.
    - **Examples**: Providing code snippets on how to subscribe to and process image data from the `/camera/depth/image_rect_raw` and `/camera/color/image_raw` topics in Python.
    - **Integration**: Demonstrating a simple application, such as using the depth data to detect obstacles.
