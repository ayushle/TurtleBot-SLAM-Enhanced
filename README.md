# TurtleBot-SLAM-Enhanced
This project showcases an advanced robotics application where we utilize a TurtleBot platform for Simultaneous Localization and Mapping (SLAM) using LiDAR, augmented with Kinect camera sensor integration for image processing, telemetry feed, and gesture control.
## 1 Prerequisites and Platform:
- Ubuntu 20.04
- Ros noetic distro [Install from here](http://wiki.ros.org/noetic/Installation/Ubuntu)
- Rviz
- Gazebo
## 2 Dependent ros package:
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
## 3 Initial Setup:
### 3.1 Install TurtleBot3 via Debian Packages.
``` bash
      sudo apt install ros-noetic-dynamixel-sdk
      sudo apt install ros-noetic-turtlebot3-msgs
      sudo apt install ros-noetic-turtlebot3
```
### 3.2 Network config:
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

### 3.3 Bring up:
Connect to bot by ssh in to it.

```bash
  ssh BOT_NAME@{IP_ADDRESS_OF_RASPBERRY_PI}
```
### 3.4 Basic packages:
Basic packages to start TurtleBot3
```bash
  export TURTLEBOT3_MODEL=${TB3_MODEL}
  roslaunch turtlebot3_bringup turtlebot3_robot.launch
```
### 3.5 Teleoperation
Teleoperation using keyboard.
```bash
  export TURTLEBOT3_MODEL=${TB3_MODEL}
  roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
For other control options check [this](https://emanual.robotis.com/docs/en/platform/turtlebot3/basic_operation/) out.
## 4 Slam
### 4.1 How it works.....
Simultaneous Localization and Mapping:
The primary sensor used for SLAM is usually a 360-degree LiDAR (Light Detection and Ranging) sensor, thus creating a 2D map of the surroundings.
Using this lidar, imu and odometry feeds orientation and positioning of bot is achived i.e. localisation takes place.
Navigating the bot using teleoperation allows to map the complete enviroment wrt. to bot's initial position.
### 4.2 Launching SLAM Node 
Follow 3.3 and 3.4 before launching below mentioned commands.
```bash
  export TURTLEBOT3_MODEL=${TB3_MODEL}
  roslaunch turtlebot3_slam turtlebot3_slam.launch
```
Launch 3.5 to intigate teleoperation for mannual navigation.
### Tuning Guide

