# TurtleBot-SLAM-Enhanced
This project showcases an advanced robotics application where we utilize a TurtleBot platform for Simultaneous Localization and Mapping (SLAM) using LiDAR, augmented with Kinect camera sensor integration for image processing, telemetry feed, and gesture control.
## Prerequisites and Platform:
- Ubuntu 20.04
- Ros noetic distro [Install from here](http://wiki.ros.org/noetic/Installation/Ubuntu)
- Rviz
- Gazebo
## Dependent ros package:
- tele op-Joy
- tele op-Keyboard
- Ros serial 
- Ros serial client
  ##### install these using below mentioned commands:
```bash
sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
```
## Initial Setup:
### Install TurtleBot3 via Debian Packages.
``` bash
      sudo apt install ros-noetic-dynamixel-sdk
      sudo apt install ros-noetic-turtlebot3-msgs
      sudo apt install ros-noetic-turtlebot3
```
### Network config:
Connect both of the system on a same wifi network.Get their respective ip.
use following command to know a systems ip.
```bash
ifconfig
```
Export these in respective systems’ .bashrc file to establish ROS master network:
  turtle bot:
```bash
  export ROS_MASTER_URI = https://IP_OF_CONTROLLER’s_PC:11311
  export ROS_HOSTNAME = IP_OF _TURTLEBOT
```
controller’s pc

```bash
  export ROS_MASTER_URI = https://IP_OF_CONTROLLERS’_PC:11311
  export ROS_HOSTNAME = IP_OF_CONTROLLER’s_PC
```

###  Bring up:
Connect to bot by Ssh in to it.

```bash
  ssh BOT_NAME@{IP_ADDRESS_OF_RASPBERRY_PI}
```
### Basic packages:
Basic packages to start TurtleBot3
```bash
  export TURTLEBOT3_MODEL=${TB3_MODEL}
  roslaunch turtlebot3_bringup turtlebot3_robot.launch
```
### Teleoperation
