# Robot-Arm-Control-using-joint_state_publisher-and-MoveIt-with-Kinematics
This repository explains controlling a robot arm using ROS tools such as joint_state_publisher and MoveIt. These tools enable the simulation, visualization, and precise kinematic control of the robot arm's movements. Key topics include setting up joint_state_publisher and configuring MoveIt.

## Repository Fork Details

The package used for this setup is a custom fork of the [original repository on GitHub](https://github.com/smart-methods/arduino_robot_arm).

## Setup Environment

- [Ubuntu 20.04](https://releases.ubuntu.com/20.04/)
- Ros 1 Noetic [How to Install It](https://github.com/justRuba/Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes/tree/main)

## Requirements
- Create a workspace
  1. Source ROS Environment
 ```bash
   source /opt/ros/noetic/setup.bash
 ```
  2. Create a Catkin Workspace
 ```bash
   mkdir -p ~/catkin_ws/src
 ```
This command creates a new directory named catkin_ws in the home directory, with a src subdirectory where we will place our ROS packages.
  3. Build the Workspace
 ```bash
   cd ~/catkin_ws/
   catkin_make
 ```
The cd command navigates to the catkin_ws directory. The catkin_make command builds the workspace, compiling all ROS packages located in the src directory.
  4. Source the Workspace Setup
 ```bash
   source devel/setup.bash
 ```
After building the workspace, this command sources the workspace's setup file to configure your environment with the workspace-specific ROS packages.
  5. Verify ROS Package Path
 ```bash
   echo $ROS_PACKAGE_PATH
 ```
  
     
