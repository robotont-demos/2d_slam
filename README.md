# SLAM 2D
This repository is a ROS package that contains 2D mapping demo showing the capabilities of the Robotont platform create a 2D map of the surrounding using different methods.

## Prerequisites installed on the Robotont on-board computer
 * [gmapping](https://wiki.ros.org/gmapping)
 * [cartographer ROS Integration (optional)](https://google-cartographer-ros.readthedocs.io/en/latest/)
 * [hector slam (optional)](http://wiki.ros.org/hector_slam)

To install gmapping, enter the following commands:<br/>
```bash
sudo apt update
sudo apt install ros-noetic-gmapping
```


## Launching the demo

**On Robotont on-board computer**

Start the SLAM 2D:
```bash
roslaunch slam_2d slam_2d.launch
```

If hector_slam or cartographer have been installed in Robotont, one can select a different method with a **mapping_method** argument. For example, to use the default gmapping:

```bash
roslaunch slam_2d slam_2d.launch mapping_method:=gmapping
```

**On PC**, visualize the result in RViz with:<br/>
```bash
roslaunch slam_2d slam_2d_display.launch
```
