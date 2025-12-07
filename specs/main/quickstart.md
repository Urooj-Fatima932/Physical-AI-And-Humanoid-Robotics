# Quickstart Guide: Setting Up Your Robotics Development Environment

This guide provides the steps to set up a complete development environment for the Physical AI & Humanoid Robotics Textbook. This setup is based on **Ubuntu 22.04 LTS**.

## 1. Ubuntu 22.04 LTS Installation

It is highly recommended to use a native Ubuntu 22.04 installation. You can also use a dual-boot setup or a virtual machine (e.g., VirtualBox, VMware) with sufficient resources (at least 4 cores, 8GB RAM, 50GB disk space recommended).

-   Download the Ubuntu 22.04 LTS ISO from the [official website](https://ubuntu.com/download/desktop).
-   Create a bootable USB drive and install Ubuntu on your machine.

## 2. ROS 2 Humble Hawksbill Installation

Follow the official ROS 2 documentation to install ROS 2 Humble on Ubuntu 22.04.

```bash
# Set locale
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

# Add ROS 2 apt repository
sudo apt install software-properties-common
sudo add-apt-repository universe
sudo apt update && sudo apt install curl
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

# Install ROS 2
sudo apt update
sudo apt install ros-humble-desktop

# Source ROS 2
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

## 3. Gazebo Simulator Installation

Gazebo is included with the `ros-humble-desktop` installation. You can test it by running:

```bash
gazebo --verbose
```

## 4. Unity Hub and Unity Editor Installation

Unity is used for high-fidelity simulation.

1.  Download and install [Unity Hub for Linux](https://unity.com/download).
2.  Open Unity Hub and create a Unity ID if you don't have one.
3.  In Unity Hub, go to the "Installs" tab and install a recent version of the Unity Editor (e.g., 2022.3.x LTS). Make sure to include "Linux Build Support (IL2CPP)" during installation.

## 5. NVIDIA Isaac Sim Setup

NVIDIA Isaac Sim requires an NVIDIA GPU. Please check the [system requirements](https://docs.omniverse.nvidia.com/isaacsim/latest/requirements.html).

1.  Download and install the [NVIDIA Omniverse Launcher](https://www.nvidia.com/en-us/omniverse/download/).
2.  Inside the Omniverse Launcher, go to the "Exchange" tab and search for "Isaac Sim".
3.  Install Isaac Sim. Note: This can be a large download.
4.  After installation, you can launch Isaac Sim from the "Library" tab.

## 6. Project Repository Setup

Finally, clone the textbook repository and set up the Docusaurus website.

```bash
# Clone the repository
git clone <repository-url>
cd physical-AI-and-humanoid-robotics-book

# Install Node.js and npm
sudo apt install nodejs npm

# Navigate to the Docusaurus project
cd classic

# Install dependencies
npm install

# Run the development server
npm start
```

Your development environment is now ready! You can access the textbook locally at `http://localhost:3000`.
