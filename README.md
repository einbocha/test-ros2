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


## Tips & Tricks
### ROS2
To create a new python package <pkg_name> with a node <node_name>, run:

(Inside the conda environment, of course)
~~~
ros2 pkg create --build-type ament_python <pkg_name> --node-name <node_name>
~~~


## Run code
### Manual
Shown below is how to run the **talker** node from pkg **pubsub** example.

Inside the ros2 workspace directory **test-ros2**, run:
1. `colcon build --packages-select pubsub`
2. `source ./install/setup.sh`
3. `ros2 run pubsub talker`

### Automatic
Shown below is how to run the **talker** node from pkg **pubsub** example.

Inside the ros2 workspace directory **test-ros2**, run: `./run.sh`

Note: If the script fails, try running `chmod +x run.sh` first.