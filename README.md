# Aqua GPS

This repository contains an underwater gps system and necessary launch files to
simulate on [Unmanned Underwater Vehicle Simulator (UUV Simulator)](https://github.com/uuvsimulator/uuv_simulator).

This work is in development at [Ingeniarius, Lda.](http://ingeniarius.pt/) and [Instituite of Systems and Robotics University of Coimbra](https://www.isr.uc.pt/) within the scope of MS thesis "Localization of an unmanned underwater vehicle using multiple water surface robots, multilateration, and sensor data fusion".

<p align="center">
  <img src="doc/imgs/aqua_gps4.png">
</p>


## Requirements

- git
- [ros-\*-desktop-full](http://wiki.ros.org/ROS/Installation)
  - kinetic
- [gazebo](http://gazebosim.org): Gazebo7 already installed with ROS.
- [CasADi](https://github.com/casadi/casadi/wiki/InstallationInstructions):

```
sudo apt-get install python-pip
sudo apt-get update
pip install casadi
```

- [UUV Simulator](https://uuvsimulator.github.io/installation.html):

```
sudo apt-get install protobuf-compiler protobuf-c-compiler
sudo apt-get install ros-kinetic-control-toolbox
cd ~/catkin_ws/src
git clone https://github.com/fredvaz/uuv_simulator.git
git clone https://github.com/fredvaz/uuv_simulation_evaluation.git

```

to install the simulator’s dependencies, you can run one of the following commands

```
cd ~/catkin_ws
rosdep install --from-paths src --ignore-src --rosdistro=kinetic -y
```

- [RexROV2](https://github.com/fredvaz/rexrov2):

```
cd ~/catkin_ws/src
git clone https://github.com/fredvaz/rexrov2
```

- [Minion USV](https://github.com/fredvaz/minion_usv/tree/minionusv_no_hydrophone)

```
cd ~/catkin_ws/src
git clone --single-branch -b minionusv_no_hydrophone https://github.com/fredvaz/minion_usv
```

## Installation 

Clone this package in the `src` folder of you catkin workspace

```
cd ~/catkin_ws/src
git clone https://github.com/ingeniarius-ltd/aqua_gps.git
```

and then build your catkin workspace

```bash
cd ~/catkin_ws
catkin_make install
```

## Running with UUV Simulator

To run a demonstration with the vehicle with teleoperation, you can run a UUV
simulator Gazebo scenario, such as

and then

```bash
roslaunch aqua_gps_demo start_aqua_gps_demo.launch
```
to move robot in a helical trajectory and visualize on rviz

```bash
roslaunch aqua_gps_demo start_aqua_gps_demo.launch move:=true rviz:=true
```

## License

Minion USV package is open-sourced under the Apache-2.0 license. See the
[LICENSE](LICENSE) file for details.
