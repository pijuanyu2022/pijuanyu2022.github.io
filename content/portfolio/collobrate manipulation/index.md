---
title: Collaborative Manipulation - In Progress
description: Web presence for mountain and travel guide
date: "2021-07-01T07:00:09+02:00"
jobDate: 2021
work: [Computer vision, Navigation, SLAM]
techs: [ROS, OpenCV, Realsense]
designs: [C++, Python]
thumbnail: images/t265.jpg
projectUrl: https://github.com/pijuanyu2022/t265_pkg
# testimonial:
#   name: John Doe
#   role: CEO @Example
#   image: sample-project/john.jpg
#   text: Prow scuttle parrel provost Sail ho shrouds spirits boom mizzenmast yardarm. Pinnace holystone mizzenmast quarter crow's nest nipperkin
---

The purpose of this project is to do the navigation, SLAM, and track an apriltag for an omnidirectional robot by using one T265 tracking camera (above). This camera will be undistorted to get a disparity map, 3D point clouds, and laser scan. Then I will use this camera to get a 2D map and avoid the obstacle.


{{< video src="apriltag track" >}}


At present, I have already successfully installed the T265 camera in the computer which is embedded in the omnidirectional robot. The camera can recognize and track the apriltag from its fisheye camera, get the position of itself and obtain the distance between apriltag and camera (watch the video above).


{{< video src="3d point cloud" >}}


I also obtain the disparity map and 3D point clouds by using some OpenCV functions and ROS packages. In the video above, the left window shows the original fisheye camera. The right window shows the disparity map which is created based on the undistorted stereo camera. The 3D point clouds are shown in the middle window. These point clouds are created based on the disparity map. They can generate a 3D image that can be used for SLAM.

{{< video src="costmap" >}}
