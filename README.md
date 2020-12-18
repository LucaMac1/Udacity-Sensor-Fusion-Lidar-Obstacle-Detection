# Sensor Fusion Self-Driving Car Course

<p align="center"><img src="docs/ObstacleDetectionFPS.gif" width="700" height="400"/></p>

### Sensor Fusion course for self-driving cars - Course 1: LIDAR.

Introduction. View lidar point clouds with Point Cloud Library (PCL).
- Point Cloud Segmentation. Program the RANSAC algorithm to segment and remove the  ground plane from a lidar point cloud. 
- Clustering. Draw bounding boxes around objects (e.g. vehicles and pedestrians) by grouping points 
		with Euclidean clustering and k-d trees. 
- Real Point Cloud Data. Apply segmentation and clustering to data streaming from a lidar  sensor on a real self-driving car. 
- Lidar Obstacle Detection Project. Filter, segment, and cluster real LIDAR point cloud data to detect vehicles and other objects.

In this course we will be talking about sensor fusion, which is the process of taking data from multiple sensors and combining it to give us a better understanding of the world around us. We will mostly be focusing on two sensors, LIDAR, and radar. By the end we will be fusing the data from these two sensors to track multiple cars on the road, estimating their positions and speed.

**Lidar** sensing gives us high resolution data by sending out thousands of laser signals. These lasers bounce off objects, returning to the sensor where we can then determine how far away objects are by timing how long it takes for the signal to return. Also, we can tell a little bit about the object that was hit by measuring the intensity of the returned signal. Each laser ray is in the infrared spectrum, and is sent out at many different angles, usually in a 360 degree range. Whilst LIDAR sensors gives us very high accurate models for the world around us in 3D, they are still quite expensive.
**Radar** data is typically very sparse and in a limited range, however it can directly tell us how fast an object is moving in a certain direction. This ability makes radars a very practical sensor for doing things like cruise control where its important to know how fast the car in front of you is traveling. Radar sensors are also very affordable and common now of days in newer cars.

**Sensor Fusion** by combing LIDAR's high resolution imaging with radar's ability to measure velocity of objects we can get a better understanding of the surrounding environment than we could using one of the sensors alone.


## Installation

### Ubuntu

```bash
$> sudo apt install libpcl-dev
$> cd ~
$> git clone https://github.com/udacity/SFND_Lidar_Obstacle_Detection.git
$> cd SFND_Lidar_Obstacle_Detection
$> mkdir build && cd build
$> cmake ..
$> make
$> ./environment
```

### Windows

https://pointclouds.org/downloads/

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

[PCL Source Github](https://github.com/PointCloudLibrary/pcl)

[PCL Mac Compilation Docs](http://www.pointclouds.org/documentation/tutorials/compiling_pcl_macosx.php)
