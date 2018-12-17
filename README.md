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

to execute, use: roslaunch <your_package_name_hector_simulador_map.launch>
