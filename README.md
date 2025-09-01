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
2.1. sudo apt install software-properties-common
2.2. sudo add-apt-repository universe

2.3. sudo apt update && sudo apt install curl gnupg lsb-release

2.4. sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

2.5. echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] \
http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | \
sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

```
## Step-3 ROS2 Environment bash setup
```bash
- for humble

# Source environment
2.6. source /opt/ros/humble/setup.bash

# Add to bashrc
2.7. echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
2.8. source ~/.bashrc

- for jazzy

# Source environment
source /opt/ros/jazzy/setup.bash

# Add to bashrc
echo "source /opt/ros/jazzy/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
## Step-3 📦 Install ROS 2 Package


# Install required software package based on your project and requirment
2.9. sudo apt update
2.10. sudo apt install ros-humble-desktop ros-humble-gazebo-ros ros-humble-joint-state-publisher ros-humble-joint-state-publisher-gui ros-humble-robot-state-publisher ros-humble-cartographer ros-humble-cartographer-ros ros-humble-gazebo-plugins ros-humble-teleop-twist-keyboard ros-humble-teleop-twist-joy ros-humble-xacro sudo ros-humble-nav2* ros-humble-urdf ros-humble-nav2-bringup ros-humble-rclpy ros-humble-gazebo-ros-pkgs ros-humble-gazebo-ros2-control ros-humble-navigation2 ros-humble-nav2-bringup ros-humble-topic-tools imagemagick ros-humble-robot-localization ros-humble-camera-calibration ros-humble-nav2-amcl

        or

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
sudo apt install ros-humblr-nav2-bringup
sudo apt install ros-humble-rclpy
sudo apt install ros-humble-gazebo-ros-pkgs
sudo apt install ros-humble-gazebo-ros2-control
sudo apt install ros-humble-navigation2
sudo apt install ros-humble-nav2-bringup
sudo apt install ros-humble-topic-tools
sudo apt install imagemagick
sudo apt install ros-humble-robot-localization
sudo apt install ros-humble-camera-calibration
sudp apt install ros-humble-nav2-amcl

# for openCV IMAGE processing
2.11. sudo apt update
2.12. sudo apt install ros-humble-cv-bridge ros-humble-vision-msgs ros-humble-vision-opencv python3-opencv libopencv-dev ros-humble-image-common tesseract-ocr libtesseract-dev
      2.12.1. pip3 install pytesseract


# for camera and image utility
2.13. sudo apt install libraspberrypi-bin v4l-utils ros-humble-v4l2-camera ros-humble-image-transport-plugins ros-humble-camera-calibration ros-humble-rqt-image-view ros-humble-image-view ros-humble-web-video-server

```


# Install required software package based on your project and requirement 
sudo apt install ros-jazzy-desktop ros-jazzy-gazebo-ros ros-jazzy-joint-state-publisher ros-jazzy-joint-state-publisher-gui ros-jazzy-robot-state-publisher ros-jazzy-cartographer ros-jazzy-cartographer-ros ros-jazzy-gazebo-plugins ros-jazzy-teleop-twist-keyboard ros-jazzy-teleop-twist-joy ros-jazzy-xacro ros-jazzy-nav2* ros-jazzy-urdf ros-jazzy-nav2-bringup ros-jazzy-rclpy ros-jazzy-gazebo-ros-pkgs ros-jazzy-gazebo-ros2-control ros-jazzy-navigation2 ros-jazzy-nav2-bringup ros-jazzy-topic-tools imagemagick ros-jazzy-robot-localization ros-jazzy-camera-calibration ros-jazzy-nav2-amcl

       or

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
sudo apt install ros-jazzy-nav2-bringup
sudo apt install ros-jazzy-rclpy
sudo apt install ros-jazzy-gazebo-ros-pkgs
sudo apt install ros-jazzy-gazebo-ros2-control
sudo apt install ros-jazzy-navigation2
sudo apt install ros-jazzy-nav2-bringup
sudo apt install ros-jazzy-topic-tools
sudo apt install imagemagick
sudo apt install ros-jazzy-robot-localization
sudo apt install ros-jazzy-camera-calibration
sudp apt install ros-jazzy-nav2-amcl


# for opencv
sudo apt install ros-jazzy-cv-bridge ros-jazzy-vision-msgs ros-jazzy-vision-opencv python3-opencv libopencv-dev ros-jazzy-image-common tesseract-ocr libtesseract-dev
pip3 install pytesseract

# for camera and image
sudo apt install libraspberrypi-bin v4l-utils ros-jazzy-v4l2-camera ros-jazzy-image-transport-plugins ros-jazzy-camera-calibration ros-jazzy-rqt-image-view ros-jazzy-image-view ros-jazzy-web-video-server
```

## 🧰 Install Colcon Build Tools
```bash
2.14. sudo apt install python3-colcon-common-extensions
2.15. sudo apt install python3-pip
2.16. pip install -U colcon-common-extensions
```
## ⚙️ Setup rosdep
```bash
2.17. sudo apt install python3-rosdep2
2.18 .sudo rosdep init
2.19 .rosdep update
2.20 .rosdep install --from-paths src --ignore-src -r -y
```
