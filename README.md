# Installation

## Prerequisites

- Ubuntu 22.04 (recommended)
- [ROS 2](https://docs.ros.org/en/rolling/Installation.html)

---

## Step-1 🔧 Setting up Locales

```bash
sudo apt update && sudo apt install locales
sudo locale-gen en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8
```

## Step-2 🏗️ Add ROS 2 Repository

```bash
sudo apt install software-properties-common
sudo add-apt-repository universe

sudo apt update && sudo apt install curl gnupg lsb-release

sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] \
http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | \
sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

sudo apt update
```

## 📦 Install ROS 2
- for humble
```bash
sudo apt update
sudo apt install ros-humble-desktop
sudo apt install ros-humble-gazebo-ros
sudo apt install ros-humble-joint-state-publisher 
sudo apt install ros-humble-joint-state-publisher-gui
sudo apt install ros-humble-robot-state-publisher 
sudo apt install ros-humble-cartographer 
sudo apt install ros-humble-cartographer-ros 
sudo apt install ros-humble-gazebo-plugins 
sudo apt install ros-humble-teleop-twist-keyboard  
sudo apt install ros-humble-teleop-twist-joy 
sudo apt install ros-humble-xacro 
sudo apt install ros-humble-nav2* 
sudo apt install ros-humble-urdf
        or
sudo apt install ros-humble-desktop ros-humble-gazebo-ros ros-humble-joint-state-publisher ros-humble-joint-state-publisher-gui ros-humble-robot-state-publisher ros-humble-cartographer ros-humble-cartographer-ros ros-humble-gazebo-plugins ros-humble-teleop-twist-keyboard ros-humble-teleop-twist-joy ros-humble-xacro sudo ros-humble-nav2* ros-humble-urdf

# Source environment
source /opt/ros/humble/setup.bash

# Add to bashrc
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
- for openCV IMAGE processing
sudo apt update
sudo apt install ros-humble-cv-bridge ros-humble-vision-msgs
```
- for jazzy
```bash
sudo apt install ros-jazzy-desktop
sudo apt update
sudo apt install ros-jazzy-desktop
sudo apt install ros-jazzy-gazebo-ros
sudo apt install ros-jazzy-joint-state-publisher 
sudo apt install ros-jazzy-joint-state-publisher-gui
sudo apt install ros-jazzy-robot-state-publisher 
sudo apt install ros-jazzy-cartographer 
sudo apt install ros-jazzy-cartographer-ros 
sudo apt install ros-jazzy-gazebo-plugins 
sudo apt install ros-jazzy-teleop-twist-keyboard  
sudo apt install ros-jazzy-teleop-twist-joy 
sudo apt install ros-jazzy-xacro 
sudo apt install ros-jazzy-nav2* 
sudo apt install ros-jazzy-urdf
       or
sudo apt install ros-jazzy-desktop ros-jazzy-gazebo-ros ros-jazzy-joint-state-publisher ros-jazzy-joint-state-publisher-gui ros-jazzy-robot-state-publisher ros-jazzy-cartographer ros-jazzy-cartographer-ros ros-jazzy-gazebo-plugins ros-jazzy-teleop-twist-keyboard ros-jazzy-teleop-twist-joy ros-jazzy-xacro ros-jazzy-nav2* ros-jazzy-urdf

# Source environment
source /opt/ros/jazzy/setup.bash

# Add to bashrc
echo "source /opt/ros/jazzy/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

## 🧰 Install Colcon Build Tools
```bash
sudo apt install python3-colcon-common-extensions
sudo apt install python3-pip
pip install -U colcon-common-extensions
```
## ⚙️ Setup rosdep
```bash
sudo apt install python3-rosdep2
sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src -r -y
```
