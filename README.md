# CatchIt - ROS Inference
This package used for autonomously search and grab objects in a large scale by unmanned aerial manipulators(UAM), which is based on ROS. We propose a novel detection and control framework for UAM to solve the problem of accurate grasping in a large-scale area, which consists of two stages: preliminary localization and precise localization. For more details, you can see [video](https://youtu.be/ycYlgfIKv6s).

Note: We only provide relevant data and models. The project is under the construction.  

![image](https://github.com/skywoodsz/CatchIt/blob/master/grasp_sucussuful.png)

## Install
We have tested on Ubuntu 16.04 with ROS Kinetic and Gazebo 7 with an NVIDIA 1050Ti with python 2.7,python 3.5 and C++11. The following steps describe the native installation.   
**1. Install ROS**   
    Follow these [instructions](http://wiki.ros.org/kinetic/Installation/Ubuntu). And we recommend installing ros-kinetic-desktop-full. 
    
**2. Install RotorS**  
    We use the RotorS as the UAV, so you should install RotorS as following these [instructions](https://github.com/ethz-asl/rotors_simulator).  
    
**3. Install jsk_recognition**  
    We use the jsk_recognition to progress the 3D infomation, you can install it as following these [instructions](https://github.com/jsk-ros-pkg/jsk_recognition).  

**4. Create a catkin workspace**
    To create a catkin workspace, follow these [instructions](http://wiki.ros.org/catkin/Tutorials/create_a_workspace):  
```
    $ mkdir -p ~/catkin_ws/src
```

```
 $ cd ~/catkin_ws/
```
