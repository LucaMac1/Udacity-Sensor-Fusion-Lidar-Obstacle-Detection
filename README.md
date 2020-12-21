# Sensor Fusion Self-Driving Car Course - Part 1

<p align="center"><img src="docs/ObstacleDetectionFPS.gif" width="700" height="400"/></p>

### Sensor Fusion course for self-driving cars - LIDAR

Introduction. View lidar point clouds with Point Cloud Library (PCL).
- Point Cloud Segmentation. Program the RANSAC algorithm to segment and remove the ground plane from a LIDAR point cloud. 
- Clustering. Draw bounding boxes around objects (e.g. vehicles and pedestrians) by grouping points with Euclidean clustering and k-d trees. 
- Real Point Cloud Data. Apply segmentation and clustering to data streaming from a LIDAR sensor on a real self-driving car. 
- Lidar Obstacle Detection Project. Filter, segment, and cluster real LIDAR point cloud data to detect vehicles and other objects.

**Lidar** sensing gives us high resolution data by sending out thousands of laser signals. These lasers bounce off objects, returning to the sensor where we can then determine how far away objects are by timing how long it takes for the signal to return. Also, we can tell a little bit about the object that was hit by measuring the intensity of the returned signal. Each laser ray is in the infrared spectrum, and is sent out at many different angles, usually in a 360 degree range. Whilst LIDAR sensors gives us very high accurate models for the world around us in 3D, they are still quite expensive.

**Radar** data is typically very sparse and in a limited range, however it can directly tell us how fast an object is moving in a certain direction. This ability makes radars a very practical sensor for doing things like cruise control where its important to know how fast the car in front of you is travelling. Radar sensors are also very affordable and common nowadays in newer cars.

**Sensor Fusion** by combing LIDAR's high resolution imaging with radar's ability to measure velocity of objects, we can get a better understanding of the surrounding environment than we could using one of the sensors alone.

GOAL: Process raw lidar data with filtering, segmentation, and clustering to detect other vehicles on the road.

## Installation

### Ubuntu

```bash
$> sudo apt install libpcl-dev
$> cd ~
$> git clone https://github.com/udacity/SFND_Lidar_Obstacle_Detection.git
$> cd SFND_Lidar_Obstacle_Detection
$> mkdir build && cd build
$> cmake -G Ninja .. 
$> ninja	      
$> ./lidar-obstacle-detection 
```

For more information about the PCL installation on Ubuntu, [check this out](https://pointclouds.org/downloads/#linux)

### Windows

vcpkg is a cross-platform open source package manager created by Microsoft, 
available for Windows, Linux and macOS. To install PCL on vcpkg-enabled 
desktops, type the following in your terminal

PS> .\vcpkg install pcl

For more information about the PCL installation on Ubuntu, [check this out](https://pointclouds.org/downloads/)

In case it is of interest, it is now published the AllInOne installers in PCL's GitHub release page. 
[Here's](https://github.com/PointCloudLibrary/pcl/releases) the one related to the latest release (scroll all the way down).

### MAC

#### Install via Homebrew
1. install [homebrew](https://brew.sh/)
2. update homebrew
	```bash
	$> brew update
	```
3. add  homebrew science [tap](https://docs.brew.sh/Taps)
	```bash
	$> brew tap brewsci/science
	```
4. view pcl install options
	```bash
	$> brew options pcl
	```
5. install PCL
	```bash
	$> brew install pcl
	```
#### Build from Source
[PCL from source on Linux](https://pcl-tutorials.readthedocs.io/en/latest/compiling_pcl_posix.html)

[PCL from source on Windows](https://pcl-tutorials.readthedocs.io/en/latest/compiling_pcl_windows.html)

[PCL Mac Compilation Docs](https://pcl-tutorials.readthedocs.io/en/latest/compiling_pcl_macosx.html)
