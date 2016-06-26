# p3at_with_sensors_for_gazebo_ros
A p3at robot model with hokuyo and camera for using with gazebo_ros package.  

I prepared a p3at xacro file with camera and hokuyo for user of the gazebo_ros envronment, and prepared some sample launch files.  
Followings are descriptions of 3 launch files.  

 * p3at_RC2016.launch :
   A prototype launch file to spawn a p3at with hokuyo and camera on.  
RC2016VRL_event1.world.  

 * spawn_p3at_RC2016.launch  
   A launch file to spawn a p3at with an own robot name, pose (x, y, z, yaw).  

* empty_world_multi_robot_example_RC2016.launch  
   A demo launch file to spawn 4 p3at robots on RC2016VRL_event1.world.  

Before use them, please change the world filename "RC2016VRL_event1.world" with your favorite one.  
And please copy required models in your world file into ~/.gazebo/models/. , copy your wotld file into 

One of 2 xacro files is a camera definition file, another one is p3at
definition file to use the camera.

Following steps are am example to use those launch files,

0. Copy the RC2016VRL_event1 sdf model folder into ~/.gazebo/models .
1. Prepare ~/pioneer3at_ws .
2. $ cd ~/pioneer3at_ws/src
3. Extract attached pioneer3at_demo_20160626_214201.zip here with overwriting .
4. $ cd ~/pioneer3at_ws
5. $ catkin_make install
6. $ roslaunch p3at_description empty_world_multi_robot_example_RC2016.launch
(Then go to another terminal.)
7. $ rosrun teleop_twist_keyboard teleop_twist_keyboard.py
cmd_vel:=/robot1/cmd_vel

Then you can see 4 p3at robots, and you can control robot1.
Have a funny time.
