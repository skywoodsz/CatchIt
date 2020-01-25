[![GPL Licence](https://badges.frapsoft.com/os/gpl/gpl.svg?v=103)](https://opensource.org/licenses/GPL-3.0/)  
[![996.icu](https://img.shields.io/badge/link-996.icu-red.svg)](https://996.icu)
[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)
# CatchIt - ROS Inference
This package used for autonomously search and grab objects in a large scale by unmanned aerial manipulators(UAM), which is based on ROS. We propose a novel detection and control framework for UAM to solve the problem of accurate grasping in a large-scale area, which consists of two stages: preliminary localization and precise localization. For more details, you can see [video](https://youtu.be/ycYlgfIKv6s).

*Note: We only provide relevant data and models. The project is under the construction.*

![image](https://github.com/skywoodsz/CatchIt/blob/master/grasp_sucussuful.png)

## Install  
We have tested on Ubuntu 16.04 with ROS Kinetic and Gazebo 7 with an NVIDIA 1050Ti with python 2.7, python 3.5 and C++11. The following steps describe the native installation.   

&ensp;**1. Install ROS**   

&ensp;&ensp;&ensp;Follow these [instructions](http://wiki.ros.org/kinetic/Installation/Ubuntu). And we recommend installing ros-kinetic-desktop-full. 
    
&ensp;**2. Install RotorS**  

&ensp;&ensp;&ensp;We use the RotorS as the UAV, so you should install RotorS as following these [instructions](https://github.com/ethz-asl/rotors_simulator).  
    
&ensp;**3. Install jsk_recognition** 

&ensp;&ensp;&ensp;We use the jsk_recognition to progress the 3D infomation, you can install it as following these [instructions](https://github.com/jsk-ros-pkg/jsk_recognition).  

&ensp;**4. Install ewok** 

&ensp;&ensp;&ensp;We use the ewok for UAV path planning, you can install it as following these [instructions](https://github.com/VladyslavUsenko/ewok).  
    
&ensp;**5. Create a catkin workspace** 

&ensp;&ensp;&ensp;To create a catkin workspace, follow these [instructions](http://wiki.ros.org/catkin/Tutorials/create_a_workspace):  
```
    $ mkdir -p ~/catkin_ws/src  # Replace `catkin_ws` with the name of your workspace
    $ cd ~/catkin_ws/
    $ catkin_make
```

&ensp;**6. Download the CatchIt code**
```
    $ cd ~/catkin_ws/src
    $ git clone https://github.com/skywoodsz/CatchIt.git
```
   
&ensp; **7. Build**
```
    $ cd ~/catkin_ws
    $ catkin_make
    $ echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
```

## Run
&ensp;**1. Start ROS master** 
```
     $ roscore
     $ cd ~/catkin_ws
     $ source devel/setup.bash
```
&ensp;**2. Run the demo world** 
```
     $ roslaunch uav_arm_gazebo firfly_planning.launch
     $ roslaunch uav_arm_gazebo firefly_control.launch
     $ roslaunch dope dope.launch
```

## Debug
- The following ROS topics are published:
```
    /filter_pcl                 # Processed point cloud
    /bounding_boxs              # 3D bounding box of potentially possible objects
    /gripper_open_close         # gripper control information
    /dope/pose_[obj_name]       # timestamped pose of object
```

&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;*Note: [obj_name] is in {cracker, gelatin, meat, mustard, soup, sugar}, for more details, you can see the [doc](https://github.com/NVlabs/Deep_Object_Pose).*  

- You can debug in RViz, add one or more of the following displays:
```
     ADD the Image -> /firefly/rgbd_uav/camera_rgb/image_raw           # camera one image(UAV overlook camera)
     ADD the Image -> /firefly/rgbd/camera_depth/camera/image_raw      # camera two image(wrist's camera)
     ADD the PointCloud2 -> /firefly/rgbd/camera_depth_2/depth/points  # camera two point cloud
     ADD the PointCloud2 -> filter_pcl                                 # Processed point cloud
     ADD the BoundingBoxArray -> /bounding_boxs                        # 3D bounding box of potentially possible objects
     ADD the Imgae -> /dope/rgb_points                                 # dope 6D estimate
```    

## Citation

## License
&ensp;&ensp;Licensed under the [GPL License](https://opensource.org/licenses/GPL-3.0/).

## Contact
&ensp;&ensp;Contact: Tianlin Zhang. Email: skywoodsz@stu.csust.edu.cn






    



    
    



    

