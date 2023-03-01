# ROS-Hardware-Interface

We use an Arduino Mega 2560 to perform the interface between the sensors and the ROS system running on the Raspberry Pi 4. There are six aspects to the code right now.

1. Establish a node, subscriber and publisher
2. Calculate the speeds of the wheels through encoder
3. Calculate coordinates based on encoder data
4. Publish the topics
5. Calculate the target velocities of each wheel based on cmd_vel
6. Control the motors using PID control.

Arduino script to establish ROS communication and PID control of a differential drive system. The target velocities to be attained by the differential drive base is given by the ROS system in terms of transational and rotational velocities. The script then calculates the target rotation for each motor and is achieved by PID.

The incremental changes in the motor shaft rotations are used to calculate the coordinates [X Y Θ]. These calculated values are then given to the ROS system in the format it requires.

The script was used as the hardware interface for a ROS based SLAM and Navigation functionality. The ROS system ran on a Raspberry Pi and this script ran on a Arduino Mega.

The folder has three files 

- hardware_interface.ino
- Motor.cpp
- Motor.h

# Mathematical Background
