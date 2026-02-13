# ROS2 Experiments


## ROS2 Version
ROS 2 Humble Hawksbill was chosen, because it was [RoboStack](https://robostack.github.io)'s best supported version at the moment of creation.

## Installation
### Notes
- conda environments are located in a subfolder of the users home directory

### Macos
1. miniforge conda variant
2. -n flag defines the environment name ```conda create -n ros2humble -c conda-forge -c robostack-humble ros-humble-desktop```
3. ```conda activate ros2humble```
4. ```conda config --env --add channels robostack-humble```
5. ```conda config --env --set channel_priority strict```
6. ```pip install colcon-common-extensions```
7. Now these commands should work:
   1. ```ros2 --help```
   2. ```rviz2```
   3. ```colcon build```
   4. ```rqt_graph```

### Raspberry Pi


## Run code
Note: For some unknown reason, do the terminals don't share the same ros2 thingy such that nodes running 
in different terminals cannot talk to each other let alone `rqt_graph` or `ros2 node list` cannot see them.

### Manual
Shown below is how to run the **talker** node from pkg **pubsub** example.

Inside the ros2 workspace directory **test-ros2**, run:
1. `colcon build --packages-select pubsub`
2. `source ./install/setup.sh`
3. `ros2 run pubsub talker`

### Automatic
Shown below is how to run a node from pkg **pubsub**.

Inside the ros2 workspace directory **test-ros2**, run: `./build.sh talker` (to run e.g. the talker node)

Note: If the script fails, try running `chmod +x build.sh` first.

## Tips & Tricks
To create a new python package <pkg_name> with a node <node_name>, run:

(Inside the conda environment, of course)
~~~
ros2 pkg create --build-type ament_python <pkg_name> --node-name <node_name>
~~~

## Resources
- [RoboStack](https://robostack.github.io)
- [Gazebo](https://gazebosim.org/docs/latest/getstarted/)
- [Conda Forge](https://conda-forge.org)
- [ROS2 Tutorial](https://www.youtube.com/playlist?list=PLLSegLrePWgJudpPUof4-nVFHGkB62Izy)
- [ROS2](https://www.ros.org)