---
id: 0001
title: Initial Constitution Definition
stage: constitution
date: 2025-12-06
surface: agent
model: claude-sonnet-4-5-20250929
feature: none
branch: master
user: user
command: /sp.constitution
labels: ["constitution"]
links:
  spec: null
  ticket: null
  adr: null
  pr: null
files:
tests:
---

## Prompt

```
/sp.constitution

Project: Physical AI & Humanoid Robotics Textbook (Hackathon I)

Core principles:
- Technical Integrity: All code must be validated, runnable, and adhere to ROS 2 Humble/Ubuntu 22.04 LTS.
- Hardware-First Context: Content must explicitly integrate or reference NVIDIA Jetson Orin and Intel RealSense D435i/D455 constraints.
- Educational Rigor: Every primary document must feature clear Learning Objectives and Knowledge Checks/Review sections.
- Docusaurus-Native: All output must be formatted for Docusaurus compatibility and use its specific components.

Key standards:
- Terminology: Enforce strict use of ISO-standard robotics terminology (e.g., Actuator, Kinematics, VSLAM).
- Formatting: Mandate Docusaurus Admonitions (:::tip, :::warning) and Code Tabs for language/version variations.
- Code Blocks: All ROS commands must use `bash` highlighting; all Python code must use `python` highlighting.
- Structure: Document hierarchy is strictly limited to three heading levels (##, ###, ####) for clean sidebar navigation.

Constraints:
- Anti-Goals: No use or reference to deprecated ROS 1 packages.
- Ethics/Safety: Every module must dedicate a section to the ethical or safety implications of the AI system being built.
- VLA Mandate: Module 4 content must explicitly cover Vision-Language-Action (VLA) integration with LLMs for high-level planning.

Success criteria:
- Content Functional: All code snippets and configurations must be functional on the target hardware (passing a spot-check).
- Formatting Validated: The content must compile successfully via `npm run build` with no Docusaurus formatting errors.
- Specification Approved: The four module specifications generated in the next step must adhere to this Constitution and be formally approved.
```

## Response snapshot

Created PHR for initial constitution definition.

## Outcome

- ✅ Impact: PHR created
- 🧪 Tests: N/A
- 📁 Files: history/prompts/constitution/0001-initial-constitution-definition.constitution.prompt.md
- 🔁 Next prompts: N/A
- 🧠 Reflection: N/A

## Evaluation notes (flywheel)

- Failure modes observed: N/A
- Graders run and results (PASS/FAIL): N/A
- Prompt variant (if applicable): N/A
- Next experiment (smallest change to try): N/A
