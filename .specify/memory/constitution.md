# Physical AI & Humanoid Robotics Textbook (Hackathon I) Constitution

## Core Principles

### Technical Integrity
All code must be validated, runnable, and adhere to ROS 2 Humble/Ubuntu 22.04 LTS.

### Hardware-First Context
Content must explicitly integrate or reference NVIDIA Jetson Orin and Intel RealSense D435i/D455 constraints.

### Educational Rigor
Every primary document must feature clear Learning Objectives and Knowledge Checks/Review sections.

### Docusaurus-Native
All output must be formatted for Docusaurus compatibility and use its specific components.

## Key Standards

### Terminology
Enforce strict use of ISO-standard robotics terminology (e.g., Actuator, Kinematics, VSLAM).

### Formatting
Mandate Docusaurus Admonitions (:::tip, :::warning) and Code Tabs for language/version variations.

### Code Blocks
All ROS commands must use `bash` highlighting; all Python code must use `python` highlighting.

### Structure
Document hierarchy is strictly limited to three heading levels (##, ###, ####) for clean sidebar navigation.

## Constraints

### Anti-Goals
No use or reference to deprecated ROS 1 packages.

### Ethics/Safety
Every module must dedicate a section to the ethical or safety implications of the AI system being built.

### VLA Mandate
Module 4 content must explicitly cover Vision-Language-Action (VLA) integration with LLMs for high-level planning.

## Success Criteria

### Content Functional
All code snippets and configurations must be functional on the target hardware (passing a spot-check).

### Formatting Validated
The content must compile successfully via `npm run build` with no Docusaurus formatting errors.

### Specification Approved
The four module specifications generated in the next step must adhere to this Constitution and be formally approved.

## Governance
Constitution supersedes all other practices; Amendments require documentation, approval, migration plan.

**Version**: 1.0.0 | **Ratified**: 2025-12-07 | **Last Amended**: 2025-12-07