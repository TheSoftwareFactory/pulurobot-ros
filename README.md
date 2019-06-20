# pulurobot-ros

Documentation about how to use this project.

------------------------------------------------------------------------------------------------------------------------------------

This project has to be used with ROS Kinetic-Kame version (wiki.ros.org/kinetic) and Gazebo 7.0 version at least (gazebosim.org/#status).

------------------------------------------------------------------------------------------------------------------------------------

ROS packages to install for this project:

gazebo-ros-pkgs (source: wiki.ros.org/gazebo_ros_pkgs)

teleop_twist_keyboard (source: http://wiki.ros.org/teleop_twist_keyboard)

slam_gmapping (source: wiki.ros.org/slam_gmapping)

move_base (source: wiki.ros.org/move_base)

frontier_exploration (source: wiki.ros.org/frontier_exploration)

RViz (source: wiki.ros.org/rviz)

Octomap (source: http://wiki.ros.org/octomap)

teb_local_planner (source: http://wiki.ros.org/teb_local_planner/Tutorials/Setup%20and%20test%20Optimization)

Packages and them dependencies are installed at the same time.

------------------------------------------------------------------------------------------------------------------------------------

How to download :

1° step:

$ cd ~/catkin_ws/src

2° step:

$ git clone https://github.com/TheSoftwareFactory/pulurobot-ros.git

3° step:

$ cd ~/catkin_ws

4° step:

$ catkin_make

If all is OK is ready to use

------------------------------------------------------------------------------------------------------------------------------------

How to launch pulu:

First step before do anything else when you launch any terminal:

$ source catkin_ws/devel/setyup.bash

after that you can do the folliwing things (if you want to use different application together you have to use an other terminal and don't forget to do the launch's first step for each terminal):

For launch pulu's gazebo only:

$ roslaunch pulurobot_gazebo pulurobot_world.launch

For launch pulu on gazebo and Rviz:

$ roslaunch pulurobot_description pulurobot_gazebo_rviz.launch

For launch pulu on gazebo and Rviz with the 2D mapping (gmapping):

$ roslaunch pulurobot_description pulurobot_gazebo_rviz_gmapping.launch

For launch the 3D mapping with octomap:

$ roslaunch pulurobot_description octomap.launch

For launch the 2D mapping with gmapping:

$ roslaunch pulurobot_description gmapping.launch

For launch pulu's 2D navigation:

$ roslaunch pulurobot_2dnav move_base.launch

For launch the keyboard teleoperation:

$ rosrun teleop_twist_keyboard teleop_twist_keyboard.py

For launch the frontier_explorer:

$ roslaunch pulurobot_2dnav no_global_map.launch


For use the keyboard teleoperation:
follow the instruction on the terminal.

For use the 2D navigation:
It's on Rviz, you have clic where you would like the pulu go with the 2D nav goal arrows tools.

For use the frontier_explorer (it's work only with the 2D navigation):
you have to do an area in Rviz with the publish point tools and when you have your area you have to click with the publish point in the area for begin the exploration.

------------------------------------------------------------------------------------------------------------------------------------

To use your own world, put your world in the worlds folder of turtle_gazebo. After, modify the turtle.launch file and change
"turtle.world" by the name of your file (line 7). To use another model in URDF, put your URDF file in turtle_description/URDF and
change "turtle.urdf" (lines 4 and 11) by your own files
