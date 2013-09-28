youbot_ros_tools
================

Use the hydro-devel branch of [Boanerghes][2] for more stable and tested code.

## Goals

+ use the kinematics and dynamics specs from [youbot-store][1].
+ use the last meshes also
+ fix the "joint issue" (joints are moving too slowly)
+ improve readability by keeping the official parameters in a parameter file

So basically this repo a massive refactor of the previous youBot repos.

## Quick start

This repo is compatible with ROS Hydro and Gazebo 1.9.

### rviz

An rviz launch is available for studying the kynematics of the robot without the physics engine.

Launch display in rviz:

```
roslaunch youbot_description youbot_rviz.launch
```

### Gazebo

This simulation currently contents the robot only.

Launch display in Gazebo:

```
roslaunch youbot_gazebo youbot_base_only.launch
```

### Dump the URDF file

It may be useful sometimes to check the generated URDF file. Use the following command to dump this file:

```
rosrun xacro xacro.py `rospack find youbot_description`/urdf/youbot.urdf.xacro -o ~/Documents/youbot.urdf
```

You can them check the integrety of this file using the urdfdom package:

```
rosrun urdfdom check_urdf ~/Documents/youbot.urdf
```

[1]: http://www.youbot-store.com/youbot-developers/software/simulation/kuka-youbot-kinematics-dynamics-and-3d-model
[2]: https://github.com/Boanerghes/youbot_ros_tools
