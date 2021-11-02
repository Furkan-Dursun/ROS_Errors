# ROS_Errors
Here I will share the errors and solutions I received in ROS

1. roslaunch: [ ] is neither a launch file in package [ ] nor is [ ] a launch file name
     - in terminal
     > gedit ~/.bashrc
     - add this to the end of the file 
     > source  ~/catkin_ws/devel/setup.bash 
     - then restart roslaunch or pc

2. [gazebo-2] process has died [pid ****, exit code ***
    - Try to fully shutdown gazebo 
    > killgazebo
    > 
    > alias killg='killall gzclient && killall gzserver && killall rosmaster'  
    
3. Could NOT find turtlebot3_msgs (missing: turtlebot3_msgs DIR)
    - You should add msgs package to the src directory 
    > cd ~/catkin_ws/src 
    - *for ros melodic*
    > git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git -b melodic-devel 
    - *for ros kinetic* 
    > git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
    > 
    > cd ~/catkin_ws && catkin_make
     
4.  RLException: Invalid <arg> tag: environment variable 'TURTLEBOT3_MODEL' is not set. 
    > export TURTLEBOT3_MODEL=waffle_pi
    - *or burger or waffle*
     
5. cannot launch node of type [amcl/amcl]: amcl 
     - *for ros melodic*
     > Sudo apt-get install ros-melodic-navigation  
     
6. Makefile:140: recipe for target 'all' failed 
     - Check cmakelists.txt
7. gazebo - no alternative certificate subject name matches target host name 'api.ignitionfuel.org'
     - Open
     > ~/.ignition/fuel/config.yaml
     - replace
     > api.ignitionfuel.org
     - with
     > fuel.ignitionrobotics.org 
     - or try this
     > api.ignitionrobotics.org
8- ERROR: cannot launch node of type [mavros/mavros_node]: can’t locate node [mavros_node] in package [mavros]
     > Remove mavros and mavlink from your ros workspace
