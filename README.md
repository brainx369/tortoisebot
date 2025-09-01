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

COLCON
.............................................................
sudo apt update
sudo apt install python3-colcon-common-extensions
sudo apt install python3-pip
pip install -U colcon-common-extensions

Destro UPDATE
.........................................................
sudo apt install python3-rosdep2
sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src -r -y



