# Tasks: Physical AI & Humanoid Robotics Textbook

**Input**: Design documents from `specs/main/`
**Prerequisites**: plan.md, spec.md files for all modules.

## Phase 1: Setup

**Purpose**: Create the directory structure for the textbook modules.

- [x] T001 [P] Create directory `classic/docs/robotics-textbook/ros2`
- [x] T002 [P] Create directory `classic/docs/robotics-textbook/digital-twin`
- [x] T003 [P] Create directory `classic/docs/robotics-textbook/ai-robot-brain`
- [x] T004 [P] Create directory `classic/docs/robotics-textbook/vla`

---

## Phase 2: Module 1 - The Robotic Nervous System (ROS 2)

**Goal**: Write the content for the ROS 2 module.

### User Story 1: ROS 2 Fundamentals
- [x] T005 [US1] Create category file `classic/docs/robotics-textbook/ros2/_category_.json`
- [x] T006 [US1] Write introduction `classic/docs/robotics-textbook/ros2/01-introduction.md`
- [x] T007 [US1] Write chapter on core concepts `classic/docs/robotics-textbook/ros2/02-core-concepts.md`

### User Story 2: Basic Publisher-Subscriber
- [x] T008 [US2] Write chapter on publisher-subscriber `classic/docs/robotics-textbook/ros2/03-publisher-subscriber.md`
- [x] T009 [US2] Write chapter on services and actions `classic/docs/robotics-textbook/ros2/04-services-actions.md`

### User Story 3: Colcon Build System
- [x] T010 [US3] Write chapter on Colcon build system `classic/docs/robotics-textbook/ros2/05-build-system-colcon.md`
- [x] T011 [US3] Write chapter on debugging tools `classic/docs/robotics-textbook/ros2/06-debugging-tools.md`

### Finalization
- [x] T012 Write chapter on ethics and safety `classic/docs/robotics-textbook/ros2/07-ethics-and-safety.md`
- [x] T013 Write knowledge check `classic/docs/robotics-textbook/ros2/08-knowledge-check.md`

---

## Phase 3: Module 2 - The Digital Twin (Gazebo & Unity)

**Goal**: Write the content for the Digital Twin module.

### User Story 1: Digital Twin Concepts
- [x] T014 [US1] Create category file `classic/docs/robotics-textbook/digital-twin/_category_.json`
- [x] T015 [US1] Write introduction `classic/docs/robotics-textbook/digital-twin/01-introduction.md`

### User Story 2: Gazebo Simulation
- [x] T016 [US2] Write chapter on Gazebo setup `classic/docs/robotics-textbook/digital-twin/02-gazebo-setup.md`
- [x] T017 [US2] Write chapter on Gazebo simulation `classic/docs/robotics-textbook/digital-twin/03-gazebo-simulation.md`

### User Story 3: Unity Simulation
- [x] T018 [US3] Write chapter on Unity setup `classic/docs/robotics-textbook/digital-twin/04-unity-setup.md`
- [x] T019 [US3] Write chapter on Unity simulation `classic/docs/robotics-textbook/digital-twin/05-unity-simulation.md`
- [x] T020 [US3] Write chapter on Sim-to-Real `classic/docs/robotics-textbook/digital-twin/06-sim-to-real.md`

### Finalization
- [x] T021 Write chapter on ethics and safety `classic/docs/robotics-textbook/digital-twin/07-ethics-and-safety.md`
- [x] T022 Write knowledge check `classic/docs/robotics-textbook/digital-twin/08-knowledge-check.md`

---

## Phase 4: Module 3 - The AI-Robot Brain (NVIDIA Isaac™)

**Goal**: Write the content for the AI-Robot Brain module.

### User Story 1: AI's Role in Robotics
- [x] T023 [US1] Create category file `classic/docs/robotics-textbook/ai-robot-brain/_category_.json`
- [x] T024 [US1] Write introduction `classic/docs/robotics-textbook/ai-robot-brain/01-introduction.md`

### User Story 2: Isaac Sim Setup
- [x] T025 [US2] Write chapter on Isaac Sim setup `classic/docs/robotics-textbook/ai-robot-brain/02-isaac-sim-setup.md`

### User Story 3: Basic AI Example
- [x] T026 [US3] Write chapter on running AI examples `classic/docs/robotics-textbook/ai-robot-brain/03-running-ai-examples.md`
- [x] T027 [US3] Write chapter on synthetic data `classic/docs/robotics-textbook/ai-robot-brain/04-synthetic-data.md`
- [x] T028 [US3] Write chapter on ROS integration `classic/docs/robotics-textbook/ai-robot-brain/05-ros-integration.md`

### Finalization
- [x] T029 Write chapter on ethics and safety `classic/docs/robotics-textbook/ai-robot-brain/06-ethics-and-safety.md`
- [x] T030 Write knowledge check `classic/docs/robotics-textbook/ai-robot-brain/07-knowledge-check.md`

---

## Phase 5: Module 4 - Vision-Language-Action (VLA)

**Goal**: Write the content for the VLA module.

### User Story 1: VLA Concepts
- [x] T031 [US1] Create category file `classic/docs/robotics-textbook/vla/_category_.json`
- [x] T032 [US1] Write introduction `classic/docs/robotics-textbook/vla/01-introduction.md`

### User Story 2: Components of VLA
- [x] T033 [US2] Write chapter on VLA architecture `classic/docs/robotics-textbook/vla/02-vla-architecture.md`

### User Story 3: VLA Examples
- [x] T034 [US3] Write chapter on VLA models `classic/docs/robotics-textbook/vla/03-vla-models.md`
- [x] T035 [US3] Write chapter on VLA applications `classic/docs/robotics-textbook/vla/04-vla-applications.md`
- [x] T036 [US3] Write chapter on limitations and future `classic/docs/robotics-textbook/vla/05-limitations-and-future.md`

### Finalization
- [x] T037 Write chapter on ethics and safety `classic/docs/robotics-textbook/vla/06-ethics-and-safety.md`
- [x] T038 Write knowledge check `classic/docs/robotics-textbook/vla/07-knowledge-check.md`

---

## Phase N: Polish & Cross-Cutting Concerns

- [x] T039 Validate Docusaurus build with `npm run build` in `classic/` directory.
- [x] T040 Review all modules for consistency and adherence to the constitution.
- [x] T041 Validate all code snippets and examples on target hardware.

---

## Dependencies & Execution Order

- **Phase 1 (Setup)**: Can be run in parallel.
- **Modules (Phase 2-5)**: Can be worked on in parallel after setup is complete.
- **Within each module**: Chapters should be written sequentially as numbered.
- **Phase N (Polish)**: Depends on all modules being complete.
