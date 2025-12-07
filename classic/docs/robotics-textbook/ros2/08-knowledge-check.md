---
sidebar_position: 8
---

# Knowledge Check: The Robotic Nervous System (ROS 2)

Congratulations on completing the ROS 2 module! It's time to test your understanding of the core concepts and practical skills you've acquired.

## Part 1: Multiple Choice Questions

Choose the best answer for each question.

### Question 1: What is the primary purpose of a ROS 2 Node?
A) To manage hardware devices in a robot.
B) To act as a single-purpose executable unit in a ROS 2 system.
C) To define communication protocols between different robots.
D) To store configuration parameters for the entire ROS 2 network.

### Question 2: Which ROS 2 communication mechanism is best suited for continuous, one-way data streams like sensor readings?
A) Services
B) Actions
C) Topics
D) Parameters

### Question 3: What is the main characteristic that distinguishes ROS 2 Services from ROS 2 Actions?
A) Services are asynchronous, while actions are synchronous.
B) Services provide continuous feedback, while actions do not.
C) Services are for long-running tasks, while actions are for quick, request-reply tasks.
D) Services are synchronous request-reply, while actions are asynchronous, cancellable, and provide feedback.

### Question 4: What is the primary function of Colcon in a ROS 2 development workflow?
A) To visualize the ROS 2 computation graph.
B) To debug communication issues between nodes.
C) To build and test ROS 2 packages and workspaces.
D) To list active ROS 2 topics and nodes.

### Question 5: Which of the following is NOT a core concept in ROS 2's communication graph?
A) Nodes
B) Topics
C) Servers
D) Parameters

## Part 2: Practical Exercise

### Task: Extend the Publisher-Subscriber Example

Modify your `py_pubsub` package to include a new publisher that publishes the current timestamp on a new topic named `/timestamp_chatter`. Then, create a new subscriber that subscribes to `/timestamp_chatter` and prints the received timestamps.

**Instructions**:
1.  Open your `~/ros2_ws/src/py_pubsub` directory.
2.  Modify `publisher_member_function.py` or create a new Python file to include a second publisher.
    *   This publisher should publish `std_msgs.msg.String` messages containing the current timestamp (e.g., using Python's `datetime` module).
    *   Publish to the `/timestamp_chatter` topic.
3.  Create a new Python file for the subscriber.
    *   This subscriber should subscribe to `/timestamp_chatter`.
    *   Print the received timestamp messages to the console.
4.  Update your `setup.py` to include the new publisher and subscriber as console scripts.
5.  Rebuild your `ros2_ws` using `colcon build --packages-select py_pubsub`.
6.  Source your workspace.
7.  Run both new nodes in separate terminals and verify they are communicating correctly.

## Answers to Multiple Choice Questions

1.  B) To act as a single-purpose executable unit in a ROS 2 system.
2.  C) Topics
3.  D) Services are synchronous request-reply, while actions are asynchronous, cancellable, and provide feedback.
4.  C) To build and test ROS 2 packages and workspaces.
5.  C) Servers (Services have servers, but "Servers" is not a core communication concept like Nodes, Topics, Actions, Parameters).
