# linefollower
The linefollower can be run by running roslaunch linefollower linefollower.launch or rosrun linefollower linefollower.py

The line follower searches for a line to follow and then follows it.

The CvBridge module converts ROS sensor_msgs/Image messages into the OpenCV image format, then is converted to RGB data and a HSV space is created. Once in an HSV space, a mask can be used at a given color range to only detect the specified color. Then the centroid is calculated to find the center of the colored section. After that a p-controller is used to ensure that the robot is persistently adjusting to stay on the line. cmd_vel commands are published to tell the robot to progress.
