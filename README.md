# ros-slam-nav

### 1. Installation
```
cd ~/catkin_ws/src/
git clone https://github.com/rifat-joy/ROS_SLAM_NAV.git
# unzip
cd catkin_ws
catkin_make
```

### 2. Simulation
 
#### 2.1. World simulation
Run the below command to open the virtual environment. 
```
roslaunch robot_gazebo robot_combination_obstacle.launch
```

To teleoperate the robot with the keyboard, launch the teleoperation node with the below command in a new terminal window.
```
roslaunch robot_teleop robot_teleop_key.launch
```

#### 2.2. SLAM simulation
The following instructions require prerequisites from the previous section. 
Open a new terminal window from the PC and run  the SLAM node. Hector SLAM method is used by default. 
```
roslaunch robot_slam robot_slam.launch slam_methods:=gmapping
```
When the map is created successfully, open a new terminal from a remote PC and save the map.
```
rosrun map_server map_saver -f ~/map
 ``` 
#### 2.3. Navigation simulation
Just like the SLAM simulation, Navigation simulation also requires prerequisites from world simulation section. 
Open a new terminal and run the Navigation node.
```
roslaunch robot_navigation robot_navigation.launch map_file:=$HOME/map.yaml
``` 

 
 



