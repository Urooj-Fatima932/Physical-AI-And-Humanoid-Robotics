# Data Model (Conceptual Entities)

This document outlines the key conceptual entities for each of the four textbook modules. These are not software data models but represent the core concepts students will learn.

## Module 1: The Robotic Nervous System (ROS 2)

- **Entity: ROS 2 Node**
  - **Description**: An independent executable process that performs a specific task within a ROS 2 system.
  - **Attributes**: Name, Namespace, Parameters.
  - **Relationships**: Communicates with other nodes via topics, services, and actions.

- **Entity: ROS 2 Topic**
  - **Description**: A communication channel for asynchronous, one-to-many message passing.
  - **Attributes**: Name, Message Type, QoS (Quality of Service) profile.
  - **Relationships**: Published by one or more nodes, subscribed to by one or more nodes.

- **Entity: ROS 2 Service**
  - **Description**: A communication mechanism for synchronous, one-to-one request-reply interactions.
  - **Attributes**: Name, Service Type (request/response).
  - **Relationships**: Provided by a server node, called by a client node.

- **Entity: Colcon Workspace**
  - **Description**: A directory structure for managing, building, and installing ROS 2 packages.
  - **Attributes**: `src`, `build`, `install`, `log` directories.

## Module 2: The Digital Twin (Gazebo & Unity)

- **Entity: Digital Twin**
  - **Description**: A virtual, dynamic model that is a real-time representation of a physical object or system.
  - **Attributes**: 3D Model, Physics Properties, Sensor Models, Actuator Models.
  - **Relationships**: Mirrors a physical robot and its environment.

- **Entity: Gazebo Simulator**
  - **Description**: An open-source 3D robotics simulator.
  - **Attributes**: World file (SDF), Models (SDF/URDF), Plugins.
  - **Relationships**: Integrates with ROS 2 for robot control and sensor data publication.

- **Entity: Unity Engine**
  - **Description**: A real-time 3D development platform used for high-fidelity simulation.
  - **Attributes**: Scene, GameObjects, Components (e.g., Rigidbody, Scripts), Assets.
  - **Relationships**: Can be connected to ROS 2 using the Unity Robotics Hub.

- **Entity: URDF (Unified Robot Description Format)**
  - **Description**: An XML format for describing the physical properties of a robot.
  - **Attributes**: Links, Joints, Visuals, Collision properties, Inertial properties.
  - **Relationships**: Imported into Gazebo or Unity to create the robot's visual and physical representation.

## Module 3: The AI-Robot Brain (NVIDIA Isaac™)

- **Entity: NVIDIA Isaac Sim**
  - **Description**: A scalable robotics simulation application for developing, testing, and training AI-based robots.
  - **Attributes**: Scene, Robot Model, Sensors, AI logic (e.g., Python scripts).
  - **Relationships**: Built on NVIDIA Omniverse. Can be integrated with ROS 2.

- **Entity: Synthetic Data Generation**
  - **Description**: The process of creating artificial datasets using simulation to train AI models.
  - **Attributes**: Data types (e.g., RGB-D images, segmentation masks), Annotations, Randomization parameters.
  - **Relationships**: A key capability of Isaac Sim used to train perception models.

- **Entity: Simulation-to-Reality (Sim-to-Real)**
  - **Description**: The process of transferring AI models and control policies trained in simulation to a physical robot.
  - **Attributes**: Domain Randomization, Model fine-tuning.
  - **Relationships**: A critical workflow in modern robotics, facilitated by high-fidelity simulators like Isaac Sim.

## Module 4: Vision-Language-Action (VLA)

- **Entity: VLA Model**
  - **Description**: An AI model that processes multimodal inputs (vision, language) to generate robotic actions.
  - **Attributes**: Vision Encoder, Language Encoder, Action Decoder.
  - **Relationships**: Forms the core of an Embodied AI system.

- **Entity: Embodied AI**
  - **Description**: An intelligent agent that learns and acts within a physical or simulated environment through a body.
  - **Attributes**: Agent, Environment, Sensors, Actuators.
  - **Relationships**: VLA models are a key enabler for Embodied AI.

- **Entity: Natural Language Understanding (NLU)**
  - **Description**: The component of a VLA model responsible for interpreting human language commands.
  - **Attributes**: Input text, Intent, Entities.
  - **Relationships**: Processes language input before it is fused with visual information.
