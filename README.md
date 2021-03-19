# ROS_Errors
Here I will share the errors and solutions I received in ROS

1. roslaunch: [ ] is neither a launch file in package [ ] nor is [ ] a launch file name
  - in terminal
     > gedit ~/.bashrc
     - add this to the end of the file 
     > source  ~/catkin_ws/devel/setup.bash 
     - then restart roslaunch or pc
