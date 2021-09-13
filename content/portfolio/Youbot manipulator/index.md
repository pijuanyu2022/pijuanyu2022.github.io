---
title: Youbot Manipulation
description: Web presence for mountain and travel guide
date: "2020-10-10T07:00:09+02:00"
jobDate: 2021
work: [Motion planning, Manipulation]
techs: [CoppeliaSim]
designs: [MATLAB]
thumbnail: images/youbot.png
projectUrl: https://github.com/pijuanyu2022/youbot-manipulation
# testimonial:
#   name: John Doe
#   role: CEO @Example
#   image: sample-project/john.jpg
#   text: Prow scuttle parrel provost Sail ho shrouds spirits boom mizzenmast yardarm. Pinnace holystone mizzenmast quarter crow's nest nipperkin
---
This project is to plans a trajectory for the end-effector of the youBot mobile manipulator (a mobile base with four mecanum wheels and a 5R robot arm), performs odometry as the chassis moves, and performs feedback control to drive the youBot to pick up a block at a specified location, carry it to a desired location, and put it down.

I use MATLAB to create an animation csv file and then input this file into CoppeliaSim so that the robot can be controlled by MATLAB. In MATLAB, I created six functions, which are
TrajectoryGenerator, FeedbackControl, FullprogramScrew, FullprogramCartesian, NextState,
and testJointLimits.


{{< video src="youbot" >}}


The above video shows the final demonstration of this project. The robot can correctly go to the position, pick up the cube and then put it in a specific position. The whole simulation can be divided into 8 steps. 

Step1: The robot will go to the position when its gripper is on the top of the cube.

Step2: The robot will move the gripper down to the grasp position.

Step3: The gripper will be closed to pick up the cube.

Step4: The robot will move the gripper back to the top of the cube.

Step5: The robot will go to the position when its gripper is on the top of the target position.

Step6: The robot will move the gripper down to the target position.

Step7: The gripper will be opened to put down the cube.

Step8: The robot will move the gripper back to the top of the target position.


