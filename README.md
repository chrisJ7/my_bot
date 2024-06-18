## Robot Package Template

This is a GitHub template. You can make your own copy by clicking the green "Use this template" button.

It is recommended that you keep the repo/package name the same, but if you do change it, ensure you do a "Find all" using your IDE (or the built-in GitHub IDE by hitting the `.` key) and rename all instances of `my_bot` to whatever your project's name is.

Note that each directory currently has at least one file in it to ensure that git tracks the files (and, consequently, that a fresh clone has direcctories present for CMake to find). These example files can be removed if required (and the directories can be removed if `CMakeLists.txt` is adjusted accordingly).

NOTES:

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
    
