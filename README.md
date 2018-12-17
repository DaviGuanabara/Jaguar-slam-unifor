# jaguar-hokuyo-hector-slam
this is autonomous system project that consist in turn jaguar an autonomous vehicle

To see more details, go to file "projeto". Configuration and installation manuals is available in appendix "Apêndice B Jaguar Autônomo". 
My full workspace is available in https://drive.google.com/open?id=1-rmqKP_5Uo2NzRpByzT1eENW1F3t4CpB.

Besides my workspace, you have to install the following libraries:

1) sudo apt-get install libsdl-image1.2-dev
2) sudo apt-get install libsdl-dev

Creating your workspace.

Basically, you have to have four packages in your workspace:

hector_mapping
hokuyo_node
drrobot_v2_player
driver_common

Finally, you have to create a package with the file hector_simulador_map.launch inside on it.


## Executing.

### First, you have to connect with LIDAR:

#### Terminal 1:
1. sudo mknod -m 666 /dev/ttyS51 c 4 115
2. sudo socat PTY,link=/dev/ttyS51, TCP4:192.168.0.60:10002

#### Terminal 2:
3. roscore

#### Terminal 3:
4. sudo chmod a=r+w /dev/pts/*
5. rosparam set hokuyo_node/port /dev/ttyS51
6. rosrun hokuyo_node hokuyo_node

#### Terminal 4:
7. rostopic echo /scan

### Second, execute hector_simulador_map
1. roslaunch <your_package_name_hector_simulador_map.launch>

### Third, start jaguar_player
rosrun drrobot_jaguarV2_player drrobot_jaguarv2_player_node

### Finally, replay cmd_vel to drrobot_cmd_vel to control jaguar
rosrun topic_tools relay cmd_vel drrobot_cmd_vel

## This project was based on:
  http://moorerobots.com/blog/post/3
  
  https://github.com/DaikiMaekawa/hector_slam_example
  
  
