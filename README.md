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
    > git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git -b melodic-devel **for ros melodic
    > git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git                  **for ros kinetic
    > cd ~/catkin_ws && catkin_make 
