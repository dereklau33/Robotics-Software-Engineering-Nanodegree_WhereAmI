# Robotics-Software-Engineering-Nanodegree_WhereAmI

# Goal
In this project, you will learn to utilize ROS AMCL package to accurately localize a mobile robot inside a map in the Gazebo simulation environments.The Robot will be given a location within the map and will efficiently move towards that goal while avoiding obstacles.  

# Summary of Tasks
1. Create a ROS package that launches a custom robot model in a custom Gazebo world  

2. Utilize the ROS AMCL package and the Tele-Operation / Navigation Stack to localize the robot  

3. Explore, add, and tune specific parameters corresponding to each package to achieve the best possible localization results  

# Project Requirements
Gazebo >= 7.0  

# Project Setup
Run Update On Linux Command Line:   
```bash
$ sudo apt-get update && sudo apt-get upgrade -y  
$ sudo apt-get install ros-kinetic-navigation  
$ sudo apt-get install ros-kinetic-map-server  
$ sudo apt-get install ros-kinetic-move-base  
$ sudo apt-get install ros-kinetic-amcl  
```  


# Project Directory
 ```bash
 .Project3                                            # Where Am I Project  
 ├── my_robot                                          
 │   ├── config                                       # Localization Parameters
 │   │   ├── MACOSX
 │   │   │   ├── ._base_local_planner_params.yaml
 │   │   │   ├── ._costmap_common_params.yaml
 │   │   │   ├── ._global_costmap_params.yaml
 │   │   │   ├── ._local_costmap_params.yaml
 │   │   ├── base_local_planner_params.yaml           # Localization Params for Local Planner
 │   │   ├── config_file.rviz                         
 │   │   ├── costmap_common_params.yaml               # Localization Params for Common Cost Map
 │   │   ├── global_costmap_params.yaml               # Localization Params for Global Cost Map
 │   │   ├── local_costmap_params.yaml                # Localization Params for Local Cost Map
 │   ├── launch      
 │   │   ├── amcl.launch                              # Launches AMCL Node
 │   │   ├── robot_description.launch                 # Launches Robot 
 │   │   ├── world.launch                             # Launches World
 │   ├── maps  
 │   │   ├── map.pgm                                  # Image of Map
 │   │   ├── my_map.yaml                              # Script of Map used by Robot
 │   ├── meshes 
 │   │   ├── hokuyo.dae                               # Sensor used by Robot
 │   ├── urdf   
 │   │   ├── my_robot.gazebo
 │   │   ├── my_robot.xacro
 │   ├── world                                        # Gazebo World containing models    
 │   │   ├── world2
 │   │   │   ├── model.config
 │   │   │   ├── model.sdf
 │   │   ├── my_world.world                           # Smaller world previously used
 │   │   ├── my_world2.world                          # Larger world used in this project
 ├── CMakeLists.txt                                   # Link libraries 
 ├── package.txt
 ├── WhereAmI_localized.png         # Image of Robot Localized at goal
 └──                              
```

# Run Instructions
Create a workspace:    
```bash
$ mkdir -p /home/workspace/catkin_ws/src
$ cd /home/workspace/catkin_ws/src
```   

Clone this Git Repository in src:    
```bash
git clone https://github.com/dereklau33/Robotics-Software-Engineering-Nanodegree_WhereAmI.git
```  

Build Package:  
```bash
$ source devel/setup.bash
$ catkin_make
```

Run Project: 
```bash
$ cd /home/workspace/catkin_ws
$ source devel/setup.bash
``` 

To Launch the Simulation:
```bash
$ roslaunch my_robot world.launch
``` 

To Launch AMCL: 
```bash
$ roslaunch my_robot amcl.launch
``` 

To Move the Robot, Select the "2D Nav Goal" Button in the Toolbar in RViz, then Click and Drag on the Map to Send the Goal to the Robot. The Robot Will Begin to Move and Localize Itself.


