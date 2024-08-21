# ROSbot Autonomous Robot

## Introduction
<p style="text-align: justify">
In this project, we will design a simulated robot, install the needed packages SLAM and Nav2, and develop a script that uses the /goal_pose topic of Nav2 to automatically navigate a new position in code (without rviz2).</p>

## My Implementation
NA.
![](showcase/picture_1.PNG)  

How to run:
1.
2. Install the needed packages
3. Launch and Build the repo
4. Run the create_goal_pose.py script

## Results
NA.

## Additional Notes
VIDEO: "Creating a rough 3D model of our robot with URDF"
Install:
    (xacro & gui) sudo apt install ros-foxy-xacro ros-foxy-joint-state-publisher-gui

Launch topics:
    colcon build --symlink-install
    source install/setup.bash
    ros2 launch my_bot rsp.launch.py use_sim_time:=true

VIDEO: "Driving your virtual robot!"
Install:
    (Gazebo) sudo apt install ros-foxy-gazebo-ros-pkgs
Launch Gazebo:
    ros2 launch gazebo_ros gazebo.launch.py
Spawn robot in Gazebo:
    ros2 run gazebo_ros spawn_entity.py -topic robot_description -entity bot_name

VIDEO: "How to use Cameras in ROS (Sim Camera and Pi Camera)"
Install:
    (image compression) sudo apt install ros-foxy-image-transport-plugins

VIDEO: "Easy SLAM with ROS using slam_toolbox"
Install:
    (SLAM) sudo apt install ros-foxy-slam-toolbox
Launch SLAM:
    ros2 launch slam_toolbox online_async_launch.py params_file:=./src/my_bot/config/mapper_params_online_async.yaml use_sim_time:=true
Install:
    (Nav2) sudo apt install ros-foxy-navigation2 ros-foxy-nav2-bringup ros-foxy-turtlebot3*
Launch map server:

VIDEO: "Making robot navigation easy with Nav2 and ROS!"
Install:
    (Nav2) sudo apt install ros-foxy-twist-mux
Launch Nav2:
    ros2 launch nav2_bringup navigation_launch.py use_sim_time:=true

Full:
Installs:
sudo apt update 
sudo apt upgrade -y
sudo apt install ros-foxy-xacro ros-foxy-joint-state-publisher-gui -y
sudo apt install ros-foxy-gazebo-ros-pkgs -y
sudo apt install ros-foxy-slam-toolbox -y
sudo apt install ros-foxy-navigation2 ros-foxy-nav2-bringup ros-foxy-turtlebot3* -y

Launchs:
cd ~/.githubs/dev_ws/
colcon build --symlink-install
source install/setup.bash
ros2 launch my_bot launch_sim.launch.py world:=./maze.world

rviz2

ros2 launch slam_toolbox online_async_launch.py params_file:=./src/my_bot/config/mapper_params_online_async.yaml use_sim_time:=true

ros2 launch nav2_bringup navigation_launch.py use_sim_time:=true

ros2 run teleop_twist_keyboard teleop_twist_keyboard
python3 create_nav2_goal_pose.py

Though, overall the CNN classifier worked well, it was not perfect. The classifier did have an issue with oddly bordered addresses. Incorrectly classified images can be seen in "Figure 10".

![](showcase/showcase_3.PNG) 
![](showcase/showcase_4.PNG) 
![](showcase/showcase_5.PNG) 
