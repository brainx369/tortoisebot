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
sudo apt install ros-humble-desktop

# Source environment
source /opt/ros/humble/setup.bash

# Add to bashrc
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
- for jazzy
```bash
sudo apt install ros-jazzy-desktop

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
```
# Run this inside your ROS workspace
```bash
rosdep install --from-paths src --ignore-src -r -y
```
