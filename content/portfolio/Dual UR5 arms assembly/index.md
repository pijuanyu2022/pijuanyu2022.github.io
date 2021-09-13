---
title: Dual UR5 Robot Arms Assembly
description: Web presence for mountain and travel guide
date: "2021-03-01T07:00:09+02:00"
jobDate: 2021
work: [Motion planning, Manipulation]
designs: [Python, Lua]
techs: [ROS, Moveit!, CoppeliaSim, Docker]
thumbnail: images/dual ur5.png
projectUrl: https://github.com/pijuanyu2022/dual_arm
# testimonial:
#   name: John Doe
#   role: CEO @Example
#   image: sample-project/john.jpg
#   text: Prow scuttle parrel provost Sail ho shrouds spirits boom mizzenmast yardarm. Pinnace holystone mizzenmast quarter crow's nest nipperkin
---
In this robot simulation, a new object will be assembled by two UR5 arms with RG2 grippers. These two UR5 arms will be controlled by the Moveit!, remote API, python3, and ROS.  The whole simulation will be done in the CoppeliaSim cross-platform. The docker approach will be helpful to make sure that everyone will run the code in the same environment with different machines and operating systems.


{{< video src="dual_arm_assemble" >}}


In this scenario, the right UR5 will pick up a primary component. The left UR5 will pick up four minor different shapes components, which are cylinder, cuboid, X-shaped column, and H-shaped column. And then they will collaborate to generate a new object with these components. 


Firstly, they will synchronously pick up the components which are put on a conveyor belt at a random position. Then they will go to the assembly position which is roughly halfway between two UR5 arms. In the third step, the left UR5 will insert the minor component into the primary component. Then it will go back to pick other components and repeat the process until all components are inserted into the primary component. In the last step, the left arm will go back to the ready position to prepare for the next component. The right arm will put this new component on a third conveyor belt. Finally, the third conveyor belt will take this new object away and the right arm will go back to the ready position.

![ros_graph](/images/ros_graph.png)


In this scenario, there are 3 child scripts in CoppeliaSim and 3 python scripts in the local environment that are used to control these two UR5 arms.


Two of these child scripts are to set the remote API and publish the UR5 joint states. These joint states will be subscribed to by two move groups. These move groups can generate trajectories based on the current joint states and the target pose. 


The last child script will publish the sensor values. A python script called Robot_control.py will subscribe to these sensor values and create some API functions. Then two UR5 controllers (Left.py and Right.py) will use these functions to read the sensor values.


In addition to these values published by the coppeliasim Ros interface, these UR5 controllers will also publish and subscribe to some parameters to connect. 


With these sensor values and parameters, the UR5 controllers will set some target positions and send these to Moveit. Then Moveit will generate the trajectory. UR5 controllers will get the trajectories and execute them.

