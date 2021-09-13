---
title: Jackbox project
description: This is my first python project
date: "2020-10-01T16:55:09+02:00"
jobDate: 2020
work: [Dynamics, Euler-Lagrange Equation]
techs: [Jupyter notebook]
designs: [Python]
thumbnail: images/jackbox.png
projectUrl: https://github.com/pijuanyu2022/jackbox
# testimonial:
#   name: John Doe
#   role: CEO @Example
#   image: sample-project/john.jpg
#   text: Prow scuttle parrel provost Sail ho shrouds spirits boom mizzenmast yardarm. Pinnace holystone mizzenmast quarter crow's nest nipperkin
---

In this project, the dynamic will be simulated through python. A jack will be animated in a box. The box will move to the upper right. And the jack will go into free fall and then impact with
the bottom of the box. After that, the jack will bounce up and rotate. And then it will impact the box again. Due to the impact of the jack, the box will also rotate and go down a little bit. But it will go up again with the external force. Then these two bodies will impact each other several times.

I assume the mass of each point of the jack and the mass of each edge of the box are all
equal to 1kg. I apply a 0.5*m*g force on the x-direction of the Box to move the Box. I assume
that the jack and box both have gravity. So, I apply an 8*m*g force on the y-direction of the Box
so that they will not go into free fall. Besides, I assume the length of the edge of the box is 4m. And the distance between two points in the Jack is 1m.

### Frames of this system

![schematic](/images/jack1.png)

In this system, Frame {w} is the world frame. Frame {A} is at the center of the Jack. Frame {F} is at the center of the box. I assume in the initial condition the Jack is at the center of the box. So, frame{A} and frame{F} are coincident temporarily.
### Result
{{< video src="jackbox" >}}

In this simulation, due to the external forces, the box moved up and right at the beginning time. The jack was falling and impacted the bottom edge of the box. After this impact, the jack bounced up to the left side of the box and then bounced again. The box went down a little bit and then went up again with the y-direction external force. Then with these two external forces and some impacts, these two bodies started to rotate and move right.
