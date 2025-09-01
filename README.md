Installation

ROS2 required setup
.......................................................................
sudo apt update && sudo apt install locales
sudo locale-gen en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

sudo apt install software-properties-common
sudo add-apt-repository universe

sudo apt update && sudo apt install curl gnupg lsb-release
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

sudo apt update 
sudo apt install ros-humble-desktop #for humble 
sudo apt install ros-jazzy-desktop #for jazzy 

source /opt/ros/humble/setup.bash #for humble 
source /opt/ros/humble/setup.bash #for jazzy

echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc #for humble 
source ~/.bashrc

echo "source /opt/ros/jazzy/setup.bash" >> ~/.bashrc #for jazzy
source ~/.bashrc

ros2 run demo_nodes_cpp talker
ros2 run demo_nodes_py listener

ros2 multicast receive
ros2 multicast send

sudo ufw allow in proto udp to 224.0.0.0/4
sudo ufw allow in proto udp from 224.0.0.0/4

