---
title: "预装软件 Pre-installed Softwares."
permalink: /pre_installed_softwares/
---

## 操作系统 Operating System
- Linux发行版 Ubuntu 16.04.5 LTS
- Linux内核 （可在grub菜单中通过Advanced进行选择，在LiveCD启动中则可以直接选择）
  - 4.15.0.43-generic HWE （硬件加强）
  - 4.4.0.141-generic LTS （长期支持）
- ROS Kinetic

## 通用软件 Application Software
- Visual Studio Code - 广受好评的跨平台 IDE  
- WPS Office WPS, - 唯一能在 Linux 平台较完美处理 office 文档的国产良心软件   
  Perfect Compatible With Microsoft (MS). Please checkout http://wps-community.org/
- 搜狗输入法 - Linux 版良心输入法  Chinese input
- proxychains - 自由切换代理  
- gimp - 功能强大的修图软件
- deepin-scrot  


## ROS功能包 ROS Packages
### 系统安装 Binary Installed
- ROS桌面完整版 ROS Desktop full
- Turtlebot与Turtlebot3
- 导航功能包集  Navigation Meta-package
- MoveIt！
- Gazebo
- PR2
- Universal Robot
- Husky
- HectorSLAM

### 源码安装 Installed from Source
- ros_tutorials
- cartographer
- 古月robot_mrobot
- 古月robot_marm
- 古月ros_advanced
- 古月PROBOT_Anno
- STDR仿真器 stdr_simulator
- 小课堂stdr_tutorials
- 小课堂ros_voice语音交互功能包 Chinese version pocketsphinx
- 慕课mooc《机器人操作系统入门》课程代码
- tianbot_racecar  

### 常用硬件驱动  Popular peripheral device drivers
其中源码安装的驱动都放在tianbot_ws中. The source code is in tianbot_ws 
- 思岚激光雷达驱动v1.9.0源码安装. 支持全系列rplidarA1, A2, A3.  
Slamtec Rplidar v1.9.0. Support all series rplidar, e.g. A1, A2 and A3
- 北阳激光雷达 urg_node.   
Hokuyo Laserscanner urg_node, tested on URG-04LX-UG01.  

- 西克激光雷达 SICK Laserscanner  

- 奥比中光深度摄像头 Obbec RGB-D Camera  
astra, astra_pro  

- RealSense深度摄像头 RGB-D Camera, R200 D415 D435
librealsense2 v2.2.1
ROS Wrapper v2.2.3

- Velodyne VLP-16
