# use-ROS-robot-with-SLAM
## installation
first we need to install the package
```
$ cd catkin_ws/src
$ git clone https://github.com/devanshdhrafani/diff_drive_bot.git
$ cd ..
$ catkin_make
```

install the dependencies :
```
$ sudo apt-get install ros-melodic-dwa-local-planner
$ sudo apt-get install ros-melodic-joy
```
## SLAM
Load the robot in the Gazebo environment,in new tab:
```
$ roslaunch diff_drive_bot gazebo.launch 
```
![rosrobotgazebo](https://user-images.githubusercontent.com/85634104/123525696-4ba1aa00-d6db-11eb-89bb-30ccff8ed308.png)

Launch the slam_gmapping node. This will also start rviz, in new tab:
```
$ roslaunch diff_drive_bot gmapping.launch
```
![rosrobotrviz](https://user-images.githubusercontent.com/85634104/123525699-50fef480-d6db-11eb-801a-1bccba97bf77.png)

to move the robot and create the map, in new tab:
```
$ rosrun diff_drive_bot keyboard_teleop.py 
```
![robotrvizmaped](https://user-images.githubusercontent.com/85634104/123525701-55c3a880-d6db-11eb-9c04-de9fe8be79a6.png)

after creating the map, we save it by :
```
$ rosrun map_server map_saver -f ~/test_map1
```
![savemap2](https://user-images.githubusercontent.com/85634104/123525814-2cefe300-d6dc-11eb-80f2-809fdc1331ab.png)


