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
## Step-3 🧰 Install Colcon Build Tools
```bash
sudo apt install python3-colcon-common-extensions
sudo apt install python3-pip
pip install -U colcon-common-extensions
```
## Step-4 ⚙️ Setup rosdep
```bash
sudo apt install python3-rosdep2
sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src -r -y
```

## Step-5 ROS2 Environment bash setup
- For HUMBLE
```bash
# Source environment
source /opt/ros/humble/setup.bash

# Add to bashrc
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
- For JAZZY
```bash
# Source environment
source /opt/ros/jazzy/setup.bash

# Add to bashrc
echo "source /opt/ros/jazzy/setup.bash" >> ~/.bashrc
source ~/.bashrc
```




## Step-6 📦 Install ROS 2 Package
- For HUMBLE
```bash

# Install required software package based on your project and requirment
sudo apt update
sudo apt install ros-humble-desktop ros-humble-gazebo-ros ros-humble-joint-state-publisher ros-humble-joint-state-publisher-gui ros-humble-robot-state-publisher ros-humble-cartographer ros-humble-cartographer-ros ros-humble-gazebo-plugins ros-humble-teleop-twist-keyboard ros-humble-teleop-twist-joy ros-humble-xacro sudo ros-humble-nav2* ros-humble-urdf ros-humble-nav2-bringup ros-humble-rclpy ros-humble-gazebo-ros-pkgs ros-humble-gazebo-ros2-control ros-humble-navigation2 ros-humble-nav2-bringup ros-humble-topic-tools imagemagick ros-humble-robot-localization ros-humble-camera-calibration ros-humble-nav2-amcl

# for camera and image utility
sudo apt install libraspberrypi-bin v4l-utils ros-humble-v4l2-camera ros-humble-image-transport-plugins ros-humble-camera-calibration ros-humble-rqt-image-view ros-humble-image-view ros-humble-web-video-server

# for openCV IMAGE processing
sudo apt update
sudo apt install ros-humble-cv-bridge ros-humble-vision-msgs ros-humble-vision-opencv python3-opencv libopencv-dev ros-humble-image-common tesseract-ocr libtesseract-dev
pip3 install pytesseract

```
- For JAZZY
```bash
# Install required software package based on your project and requirement
sudo apt install ros-jazzy-desktop ros-jazzy-gazebo-ros ros-jazzy-joint-state-publisher ros-jazzy-joint-state-publisher-gui ros-jazzy-robot-state-publisher ros-jazzy-cartographer ros-jazzy-cartographer-ros ros-jazzy-gazebo-plugins ros-jazzy-teleop-twist-keyboard ros-jazzy-teleop-twist-joy ros-jazzy-xacro ros-jazzy-nav2* ros-jazzy-urdf ros-jazzy-nav2-bringup ros-jazzy-rclpy ros-jazzy-gazebo-ros-pkgs ros-jazzy-gazebo-ros2-control ros-jazzy-navigation2 ros-jazzy-nav2-bringup ros-jazzy-topic-tools imagemagick ros-jazzy-robot-localization ros-jazzy-camera-calibration ros-jazzy-nav2-amcl

# for camera and image
sudo apt install libraspberrypi-bin v4l-utils ros-jazzy-v4l2-camera ros-jazzy-image-transport-plugins ros-jazzy-camera-calibration ros-jazzy-rqt-image-view ros-jazzy-image-view ros-jazzy-web-video-server

# for opencv
sudo apt install ros-jazzy-cv-bridge ros-jazzy-vision-msgs ros-jazzy-vision-opencv python3-opencv libopencv-dev ros-jazzy-image-common tesseract-ocr libtesseract-dev
pip3 install pytesseract

```
## Step-7 📦 Create Workspace
- For Humble
```bash
# create the work space directory and src folder under that clone the repo and performe below task
vboxuser@ubuntu-22:~$ mkdir -p humble_ws/src
vboxuser@ubuntu-22:~$ cd humble_ws/src
vboxuser@ubuntu-22:~/humble_ws/src$
boxuser@ubuntu-22:~/humble_ws/src$ git clone -b ros2-humble https://github.com/rigbetellabs/tortoisebot.git
vboxuser@ubuntu-22:~/humble_ws$ colcon build
vboxuser@ubuntu-22:~/humble_ws$ source install/setup.bash
```
- For Jazzy
```bash
# create the work space directory and src folder under that clone the repo and performe below task
vboxuser@ubuntu-22:~$ mkdir -p jazzy_ws/src
vboxuser@ubuntu-22:~$ cd jazzy_ws/src
vboxuser@ubuntu-22:~/jazzy_ws/src$
vboxuser@ubuntu-22:~/jazzy_ws/src$ git clone -b ros2-jazzy https://github.com/rigbetellabs/tortoisebot.git
vboxuser@ubuntu-22:~/jazzy_ws$ colcon build
vboxuser@ubuntu-22:~/jazzy_ws$ source install/setup.bash
```
## Step-8 📦 Run the final command For simulation
- For simulation
```bash
vboxuser@ubuntu-22:~/jazzy_ws$ ros2 launch tortoisebot_bringup autobringup.launch.py use_sim_time:=True exploration:=True
```
## Step-8 📦 Run the final command For Real Robot

```bash
vboxuser@ubuntu-22:~/jazzy_ws$ ros2 launch tortoisebot_bringup autobringup.launch.py use_sim_time:=False exploration:=True
```
## Step-9 Run the below command when you want to add and create your own package or node in ros2
```bash
vboxuser@ubuntu-22:~$ mkdir -p my_ws/src
vboxuser@ubuntu-22:~$ cd my_ws/src
vboxuser@ubuntu-22:~/my_ws/src$
vboxuser@ubuntu-22:~/my_ws/src$ ros2 pkg create simple_pkg
vboxuser@ubuntu-22:~/my_ws$ colcon build
vboxuser@ubuntu-22:~/my_ws$ source install/setup.bash
```
