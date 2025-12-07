# Implementation Plan: Physical AI & Humanoid Robotics Textbook

**Branch**: `main` | **Date**: 2025-12-07 | **Spec**: [specs/1-robotics-textbook-modules](specs/1-robotics-textbook-modules)
**Input**: Generate a comprehensive, sequenced project execution plan based on the four approved module specifications.

## Summary

This project will create four modules for a Physical AI & Humanoid Robotics Textbook. The modules are: "The Robotic Nervous System (ROS 2)", "The Digital Twin (Gazebo & Unity)", "The AI-Robot Brain (NVIDIA Isaac™)", and "Vision-Language-Action (VLA)". The final output will be a set of Docusaurus-compatible Markdown documents, written sequentially and adhering to the project's constitution.

## Technical Context

**Language/Version**: Python 3.10, C++, Docusaurus (React/Markdown)
**Primary Dependencies**: ROS 2 Humble, Gazebo, Unity, NVIDIA Isaac™ Sim, Docusaurus
**Storage**: N/A (Markdown files)
**Testing**: Manual testing of user stories, `npm run build` for Docusaurus site validation.
**Target Platform**: Ubuntu 22.04 LTS, NVIDIA Jetson Orin, Intel RealSense D435i/D455, Docusaurus.
**Project Type**: Web Application (Docusaurus documentation).
**Performance Goals**: Educational clarity and correctness. All code snippets must be functional on target hardware.
**Constraints**: Must adhere to Docusaurus formatting rules, including a maximum of three heading levels. No use of deprecated ROS 1 packages. Content must be hardware-aware, referencing the NVIDIA Jetson Orin and Intel RealSense cameras.
**Scale/Scope**: Four distinct textbook modules, each with multiple chapters.

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

- **Technical Integrity**: All code must be validated, runnable, and adhere to ROS 2 Humble/Ubuntu 22.04 LTS. (*NEEDS VERIFICATION*)
- **Hardware-First Context**: Content must explicitly integrate or reference NVIDIA Jetson Orin and Intel RealSense D435i/D455 constraints. (*NEEDS VERIFICATION*)
- **Educational Rigor**: Every primary document must feature clear Learning Objectives and Knowledge Checks/Review sections. (*NEEDS VERIFICATION*)
- **Docusaurus-Native**: All output must be formatted for Docusaurus compatibility and use its specific components. (*NEEDS VERIFICATION*)
- **Terminology**: Enforce strict use of ISO-standard robotics terminology. (*NEEDS VERIFICATION*)
- **Formatting**: Mandate Docusaurus Admonitions (:::tip, :::warning) and Code Tabs. (*NEEDS VERIFICATION*)
- **Code Blocks**: All ROS commands must use `bash` highlighting; all Python code must use `python` highlighting. (*NEEDS VERIFICATION*)
- **Structure**: Document hierarchy is strictly limited to three heading levels (##, ###, ####). (*NEEDS VERIFICATION*)
- **Anti-Goals**: No use or reference to deprecated ROS 1 packages. (*NEEDS VERIFICATION*)
- **Ethics/Safety**: Every module must dedicate a section to the ethical or safety implications. (*NEEDS VERIFICATION*)
- **VLA Mandate**: Module 4 must cover Vision-Language-Action (VLA) integration with LLMs. (*NEEDS VERIFICATION*)

## Project Structure

### Documentation (this feature)

```text
specs/1-robotics-textbook-modules/
├── plan.md              # This file
├── research.md          # Phase 0 output
├── data-model.md        # Phase 1 output
├── quickstart.md        # Phase 1 output
└── tasks.md             # Phase 2 output (/sp.tasks command)
```

### Source Code (repository root)

The textbook content will be located within the existing Docusaurus project structure at `classic/docs/robotics-textbook`.

**Structure Decision**: The project is a documentation website built with Docusaurus. The file structure will follow the standard Docusaurus conventions for creating new documentation sections. A new directory `robotics-textbook` will be created inside `classic/docs` to house the four modules.

### Writing Sequence and File Paths

The modules and chapters will be written in the following sequence.

**Module 1: The Robotic Nervous System (ROS 2)**
1.  `classic/docs/robotics-textbook/ros2/_category_.json`
2.  `classic/docs/robotics-textbook/ros2/01-introduction.md`
3.  `classic/docs/robotics-textbook/ros2/02-core-concepts.md`
4.  `classic/docs/robotics-textbook/ros2/03-publisher-subscriber.md`
5.  `classic/docs/robotics-textbook/ros2/04-services-actions.md`
6.  `classic/docs/robotics-textbook/ros2/05-build-system-colcon.md`
7.  `classic/docs/robotics-textbook/ros2/06-debugging-tools.md`
8.  `classic/docs/robotics-textbook/ros2/07-ethics-and-safety.md`
9.  `classic/docs/robotics-textbook/ros2/08-knowledge-check.md`

**Module 2: The Digital Twin (Gazebo & Unity)**
1.  `classic/docs/robotics-textbook/digital-twin/_category_.json`
2.  `classic/docs/robotics-textbook/digital-twin/01-introduction.md`
3.  `classic/docs/robotics-textbook/digital-twin/02-gazebo-setup.md`
4.  `classic/docs/robotics-textbook/digital-twin/03-gazebo-simulation.md`
5.  `classic/docs/robotics-textbook/digital-twin/04-unity-setup.md`
6.  `classic/docs/robotics-textbook/digital-twin/05-unity-simulation.md`
7.  `classic/docs/robotics-textbook/digital-twin/06-sim-to-real.md`
8.  `classic/docs/robotics-textbook/digital-twin/07-ethics-and-safety.md`
9.  `classic/docs/robotics-textbook/digital-twin/08-knowledge-check.md`

**Module 3: The AI-Robot Brain (NVIDIA Isaac™)**
1.  `classic/docs/robotics-textbook/ai-robot-brain/_category_.json`
2.  `classic/docs/robotics-textbook/ai-robot-brain/01-introduction.md`
3.  `classic/docs/robotics-textbook/ai-robot-brain/02-isaac-sim-setup.md`
4.  `classic/docs/robotics-textbook/ai-robot-brain/03-running-ai-examples.md`
5.  `classic/docs/robotics-textbook/ai-robot-brain/04-synthetic-data.md`
6.  `classic/docs/robotics-textbook/ai-robot-brain/05-ros-integration.md`
7.  `classic/docs/robotics-textbook/ai-robot-brain/06-ethics-and-safety.md`
8.  `classic/docs/robotics-textbook/ai-robot-brain/07-knowledge-check.md`

**Module 4: Vision-Language-Action (VLA)**
1.  `classic/docs/robotics-textbook/vla/_category_.json`
2.  `classic/docs/robotics-textbook/vla/01-introduction.md`
3.  `classic/docs/robotics-textbook/vla/02-vla-architecture.md`
4.  `classic/docs/robotics-textbook/vla/03-vla-models.md`
5.  `classic/docs/robotics-textbook/vla/04-vla-applications.md`
6.  `classic/docs/robotics-textbook/vla/05-limitations-and-future.md`
7.  `classic/docs/robotics-textbook/vla/06-ethics-and-safety.md`
8.  `classic/docs/robotics-textbook/vla/07-knowledge-check.md`

## Phase 0: Outline & Research

The following points need clarification and will be researched. The findings will be documented in `research.md`.

1.  **Python Version**: Confirm the standard Python version for ROS 2 Humble on Ubuntu 22.04. (Assumed 3.10)
2.  **ISO Terminology**: Compile a list of key ISO-standard robotics terms to be used consistently across all modules.
3.  **Docusaurus Components**: Identify any advanced Docusaurus components (beyond admonitions and code tabs) that can enhance the educational experience.
4.  **Hardware-Specific Examples**: Research and outline specific code examples and configurations that target the NVIDIA Jetson Orin and Intel RealSense cameras.

## Phase 1: Design & Contracts

**Prerequisites**: `research.md` complete

1.  **Data Model**: The `data-model.md` will not describe a software data model, but will outline the key conceptual entities, their attributes, and relationships for each of the four textbook modules, based on the "Key Entities" section of each specification.
2.  **API Contracts**: No API contracts will be generated as this is a documentation project.
3.  **Quickstart Guide**: A `quickstart.md` will be created to provide students with a comprehensive guide to setting up their development environment. This will include:
    -   Installing Ubuntu 22.04 LTS
    -   Installing ROS 2 Humble
    -   Installing Gazebo
    -   Installing Unity Hub and Unity Editor
    -   Setting up NVIDIA Isaac Sim
    -   Cloning the project repository and running the Docusaurus site locally.
4.  **Agent Context Update**: Run `.specify/scripts/powershell/update-agent-context.ps1 -AgentType gemini` to update the agent's context with the technologies used in this plan.

## Complexity Tracking

> No constitution violations are anticipated. This section will be filled only if necessary.

| Violation | Why Needed | Simpler Alternative Rejected Because |
|-----------|------------|-------------------------------------|
|           |            |                                     |
