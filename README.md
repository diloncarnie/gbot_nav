# gbot_nav package setup guide

![ROS](https://img.shields.io/badge/ros2-humble-blue)

This is a ros package for setting up and running nav2 using the unity simulation. The following are step by step instructions on how to connect nav2 to the unity.

---

## Setup Instructions
1. Open a new terminal and connect to unity via ros-tcp-endpoint

    ```bash
	source install/setup.bash
    ros2 run ros_tcp_endpoint default_server_endpoint --ros-args -p ROS_IP:=<your IP address>
	```
Use `hostname -I` to find out your IP address

1. Run the display.launch.py file in a new terinal

    ```bash
	source install/setup.bash
    ros2 launch gbot_nav display.launch.py
	```

1. Run the slam_toolbox package in a new terminal

    ```bash
	source install/setup.bash
    ros2 launch slam_toolbox online_async_launch.py
	```

1. Run t he nav2_bringup package in a new terminal

    ```bash
	source install/setup.bash
    ros2 launch nav2_bringup navigation_launch.py use_sim_time:=true params_file:=$HOME/ros2_ws/src/gbot_nav/config/nav2_params.yaml

	```
    