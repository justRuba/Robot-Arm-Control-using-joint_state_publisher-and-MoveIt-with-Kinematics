# Robot-Arm-Control-using-joint_state_publisher-and-MoveIt-with-Kinematics
This repository explains controlling a robot arm using ROS tools such as joint_state_publisher and MoveIt. These tools enable the simulation, visualization, and precise kinematic control of the robot arm's movements. Key topics include setting up joint_state_publisher and configuring MoveIt.

## Reference Repository 

The package used for this setup is a custom fork of the [original repository on GitHub](https://github.com/smart-methods/arduino_robot_arm).

## Setup Environment

- [Ubuntu 20.04](https://releases.ubuntu.com/20.04/)
- Ros 1 Noetic [How to Install It](https://github.com/justRuba/Installing-and-Running-Your-First-ROS-1-and-ROS-2-Nodes/tree/main)

## Requirements
- Create a workspace

Source ROS Environment 
 ```bash
   source /opt/ros/noetic/setup.bash
 ```
Create a Catkin Workspace
 ```bash
   mkdir -p ~/catkin_ws/src
 ```
This command creates a new directory named catkin_ws in the home directory, with a src subdirectory where we will place our ROS packages.

Build the Workspace 
 ```bash
   cd ~/catkin_ws/
   catkin_make
 ```
The cd command navigates to the catkin_ws directory. The catkin_make command builds the workspace, compiling all ROS packages located in the src directory.

Source the Workspace Setup 
 ```bash
   source devel/setup.bash
 ```
After building the workspace, this command sources the workspace's setup file to configure your environment with the workspace-specific ROS packages.

Verify ROS Package Path 
 ```bash
   cd ~/catkin_ws/src
   sudo apt install https://github.com/smart-methods/arduino_robot_arm
 ```

- Add the (arduino_robot_arm) package to src
```bash
  cd ~/catkin_ws
  rosdep install --from-paths src --ignore-src -r -y
  sudo apt-get install ros-noetic-moveit
  sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
  sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher
  sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
```


- Install all the dependencies
```bash
  cd ~/catkin_ws
  rosdep install --from-paths src --ignore-src -r -y
  sudo apt-get install ros-noetic-moveit
  sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
  sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher
  sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
  catkin_make
```

## Controlling the robot arm using joint_state_publisher

joint_state_publisher is a ROS tool that publishes the state of a robot’s joints, including their positions, velocities, and efforts. It is commonly used for visualizing and simulating robot movements in tools like RViz. The tool also provides a GUI for manually adjusting joint positions, aiding in testing and debugging.

 ```bash
   sudo apt-get install ros-noetic-robot-state-publisher
 ```

The command sudo apt-get install ros-noetic-robot-state-publisher installs the robot_state_publisher package in ROS Noetic, which publishes the robot's joint and link states for visualization and simulation.

 ```bash
   roslaunch robot_arm_pkg check_motors.launch
 ```

The command roslaunch robot_arm_pkg check_motors.launch launches the check_motors file from the robot_arm_pkg package, typically used to start nodes for testing and verifying the robot arm's motors.

![WhatsApp Image 2024-07-22 at 23 45 54_6ab01034](https://github.com/user-attachments/assets/8ecdf662-196b-448a-a903-35e993e8e611)

 ```bash
   roslaunch robot_arm_pkg check_motors_gazebo.launch
 ```
The command roslaunch robot_arm_pkg check_motors_gazebo.launch launches a Gazebo simulation for testing the robot arm's motors within the robot_arm_pkg package.

![WhatsApp Image 2024-07-22 at 21 47 55_187b1c26](https://github.com/user-attachments/assets/79e24626-37ad-4edd-82e9-cef72088918d)

## Controlling the robot arm using Moveit and kinematics

MoveIt is a ROS framework for motion planning and control of robotic arms, enabling tasks like path planning and collision avoidance. It uses kinematics to calculate the robot's end-effector position based on joint angles, facilitating precise movement control and execution.

 ```bash
   roslaunch moveit_pkg demo.launch
 ```

![WhatsApp Image 2024-07-22 at 23 49 34_ccfcd847](https://github.com/user-attachments/assets/a09d7558-322f-40fe-879d-e412f37a114c)

