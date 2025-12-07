---
sidebar_position: 5
---

# Chapter 5: The Colcon Build System

So far, we've written ROS 2 nodes and created our own package. But how does ROS 2 find, build, and execute our code? The answer is the **Colcon build system**.

`colcon` (short for "collective construction") is the command-line tool used to build and test ROS 2 packages. It's a versatile tool that can handle different build systems and package types.

## Colcon Workspaces

A **Colcon workspace** is a directory that contains your ROS 2 packages. It's the top-level directory where you will do most of your development work. A typical Colcon workspace has the following structure:

-   `src/`: This is where you will place the source code for your ROS 2 packages.
-   `build/`: Colcon creates this directory to store intermediate build files. You usually don't need to interact with it directly.
-   `install/`: After a successful build, this directory will contain the installed files for your packages, including executables and shared libraries.
-   `log/`: Colcon stores logs of the build process here, which can be useful for debugging build issues.

## The Build Lifecycle

Developing with Colcon involves a simple, repeatable lifecycle:

1.  **Create a Workspace**: Create a directory for your workspace and a `src` directory inside it.

    ```bash
    mkdir -p ~/ros2_ws/src
    cd ~/ros2_ws
    ```

2.  **Add Packages**: Clone or create your ROS 2 packages inside the `src` directory.

3.  **Build Packages**: From the root of your workspace, run `colcon build`.

    ```bash
    colcon build
    ```

    Colcon will automatically find all the ROS 2 packages in your `src` directory and build them. You can also build specific packages:

    ```bash
    colcon build --packages-select py_pubsub
    ```

4.  **Source the Environment**: Before you can run any of the executables from your newly built packages, you need to "source" the setup files in the `install` directory. This command adds your workspace's packages to your shell's environment, allowing ROS 2 to find them.

    ```bash
    source install/setup.bash
    ```

    **Important**: You need to do this in every new terminal you open. It's common to add this command to your shell's startup script (e.g., `~/.bashrc`).

5.  **Run your Nodes**: Now you can run the executables from your packages using `ros2 run`.

    ```bash
    ros2 run py_pubsub talker
    ```

## Understanding `package.xml` and `setup.py`

Colcon relies on two important files in your package to know how to build it:

-   `package.xml`: This is a manifest file that contains metadata about your package, such as its name, version, author, and, most importantly, its dependencies. Colcon uses this file to ensure all necessary dependencies are installed before building your package.

-   `setup.py` (for Python packages): This file tells Python's setuptools how to install your package. This is where you define your package's executables (in the `entry_points` section), as we did in the previous chapter.

By understanding the Colcon build system and its conventions, you gain the power to create, manage, and share your own robotics software within the ROS 2 ecosystem.
