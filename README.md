# 2d_slam

![ROS 2](https://img.shields.io/badge/ROS2%20-Jazzy-blue.svg) ![License](https://img.shields.io/badge/License-Apache_2.0-green.svg)

## **Overview**
SLAM 2D demo for Robotont (ROS 2).
## **Table of Contents**
- [Installation](#installation)
- [Dependencies](#dependencies)
- [Building the Package](#building-the-package)
- [Launch Files](#launch-files)
- [License](#license)

---

## **Installation**

### **1. Clone the Repository**
```bash
cd ~/<YOUR_WORKSPACE_NAME_HERE>/src
git clone https://github.com/robotont-demos/2d_slam.git
```

## **Dependencies**
### **1. List of dependencies**
1.1. robotont_navigation<br>
1.2. depthimage_to_laserscan
### **2. Install dependencies**
```bash
cd ~/<YOUR_WORKSPACE_NAME_HERE>
rosdep install --from-paths src --ignore-src -r -y
```

## **Building the package**
```bash
cd ~/<YOUR_WORKSPACE_NAME_HERE>
colcon build --packages-select 2d_slam
```

## **Launch files**
### **1. Source workspace**
```bash
source ~/<YOUR_WORKSPACE_NAME_HERE>/install/setup.bash
```
## 2. Available Launch Files

### 2.1. `nav2_lidar_slam.launch.py`
Launch navigation (Nav2) and SLAM (using LIDAR as the main sensor) together. Also publishes a fixed transform for a LIDAR on a custom frame.
### Supported Parameters

| Name         | Description                      | Default                        |
|--------------|----------------------------------|--------------------------------|
| `use_sim_time` | Use simulation time (for sim)    | `true`                         |
| `params_file`  | Nav2 parameter YAML file         | `config/nav/nav2_realsense.yaml`|
| `image`        | (Unused, kept for compatibility) | `/camera/depth/image_raw`      |
| `info`         | (Unused, kept for compatibility) | `/camera/color/camera_info`    |
| `scan`         | LIDAR scan topic                | `/scan`                        |

---

**Usage:**
```bash
ros2 launch demo_slam nav2_lidar_slam.launch.py
```

### 2.2. `nav2_realsense_slam.launch.py`
Launch navigation (Nav2), SLAM Toolbox, and conversion of a depth image (from an Intel Realsense camera) to a 2D laser scan for SLAM.
### Supported Parameters

| Name         | Description                      | Default                        |
|--------------|----------------------------------|--------------------------------|
| `use_sim_time` | Use simulation time (for sim)    | `true`                         |
| `params_file`  | Nav2 parameter YAML file         | `config/nav/nav2_realsense.yaml`|
| `image`        | Depth image topic | `/camera/depth/image_raw`      |
| `info`         | Camera info topic | `/camera/color/camera_info`    |
| `scan`         | Output LaserScan topic                | `/scan`                        |

---

**Usage:**
```bash
ros2 launch demo_slam nav2_realsense_slam.launch.py
```

### 2.3. `rviz2_visualize_costmaps.launch.py`
Launches RViz2 with a preconfigured layout for visualizing the robot's costmaps and state.

**Usage:**
```bash
ros2 launch demo_slam rviz2_visualize_costmaps.launch.py
```

## **License**
This project is licensed under the Apache 2.0 license - see the [LICENSE](LICENSE) file for more information.
