![](./images/Picto+STEREOLABS_Black.jpg)

# Stereolabs ZED Camera - ROS Integration
Fixed By Jack Fields To Run Properly on Nvidia Xavier, running Ubuntu 18.04 with Ros Melodic


## Getting started

- First, download the latest version of the ZED SDK on [stereolabs.com](https://www.stereolabs.com/developers/)
- [Install](#build-the-program) the ZED ROS wrapper.
- For more information, check out our [ROS documentation](https://www.stereolabs.com/documentation/guides/using-zed-with-ros/introduction.html) or our [ROS wiki](http://wiki.ros.org/zed-ros-wrapper). If you want to customize the wrapper, check the [ZED API documentation](https://www.stereolabs.com/developers/documentation/API/).

### Prerequisites

- Ubuntu 16.04 // Fixed to Ubuntu 18.04
- [ZED SDK **≥ 2.3**](https://www.stereolabs.com/developers/) and its dependency [CUDA](https://developer.nvidia.com/cuda-downloads)
- [ROS Kinetic](http://wiki.ros.org/kinetic/Installation/Ubuntu)
- Note That these must be installed before hand, The patch I applied to this removes the check for CUDA and the ZED SDK fixing one of the issues we ran into

### Build the program 

The zed_ros_wrapper is a catkin package. It depends on the following ROS packages:

   - tf2_ros
   - tf2_geometry_msgs
   - nav_msgs
   - roscpp
   - rosconsole
   - sensor_msgs
   - stereo_msgs
   - image_transport
   - dynamic_reconfigure
   - urdf
   - diagnostic_updater

Open a terminal and build the package:

    cd ~/catkin_ws/src
    git clone https://github.com/JackFields/zed-ros-wrapper
    cd ../
    catkin_make
    source ./devel/setup.bash

### Run the program

To launch the wrapper [along with an Rviz preview](./zed_display_rviz), open a terminal and launch:

    $ roslaunch zed_display_rviz display.launch # by default open a ZED

or

    $ roslaunch zed_display_rviz display_zedm.launch # open a ZED Mini


To launch the wrapper without Rviz, use:

    $ roslaunch zed_wrapper zed.launch

 To select the ZED from its serial number

    $ roslaunch zed_wrapper zed.launch serial_number:=1010 #replace 1010 with the actual SN
    
### For instructions on how to use this software properly refer to the original repository
