---
title: "Autonomous Rover Navigation for Search & Rescue"
excerpt: "ROS2 autonomous navigation system with obstacle avoidance and vision-based target detection"
order: 2
collection: portfolio
image: /images/Rover.png
---

This project was developed as an R&D effort for the Oregon State University Mars Rover Team to support the autonomous search phase of international rover competitions. I designed a modular ROS2 software stack that enables a simulated rover to autonomously navigate cluttered environments, avoid obstacles using LiDAR, and detect colored targets through computer vision. The project emphasized robust autonomous behavior, modular software architecture, and realistic simulation-based testing in Gazebo.

<img src="/images/sim_sc.png" alt="Gazebo rover simulation" style="max-width:700px;">

## Highlights

- Designed a modular ROS2 architecture consisting of independent navigation, obstacle avoidance, and vision nodes
- Implemented a Bug-based obstacle avoidance algorithm using LiDAR and proportional wall-following control
- Developed an OpenCV vision pipeline for autonomous flag detection with temporal filtering to eliminate false positives
- Created a custom LiDAR simulation node after limitations were discovered in the native Gazebo sensor implementation
- Integrated waypoint navigation, obstacle avoidance, and vision into a complete autonomous search pipeline

## Technical Stack

**Software:** ROS2 · Python · OpenCV · Gazebo  
**Algorithms:** Bug Navigation · Proportional Control · Waypoint Navigation  
**Sensors:** Simulated LiDAR · RGB Camera · Odometry

## System Overview

<img src="/images/diagram.png" alt="ROS2 node architecture" style="max-width:700px;">

The system is organized into three primary ROS2 nodes:

- **Navigation:** Drives the rover through predefined waypoints using proportional heading control while monitoring obstacle and vision data.
- **Obstacle Avoidance:** Implements a Bug-style navigation algorithm that transitions into wall following when obstacles are detected and returns to the planned path once a clear route is available.
- **Vision:** Processes RGB camera images with OpenCV contour detection to identify red flags. A temporal confirmation filter requiring 4 of the previous 5 frames prevents false detections before signaling the navigation node.

<table>
<tr>
<td align="center" width="50%">

<img src="/images/bugmode.png" alt="Bug algorithm visualization" style="max-width:100%;">

**Bug-Based Navigation**

LiDAR-based obstacle avoidance with wall-following behavior.

</td>

<td align="center" width="50%">

<img src="/images/flagcam.png" alt="Flag detection" style="max-width:100%;">

**Vision Detection**

OpenCV contour detection with temporal confirmation.

</td>
</tr>
</table>

## Results & Validation

The complete system was validated in Gazebo simulation through repeated autonomous navigation trials.

- Successfully navigated multi-waypoint search paths with proportional heading control
- Reliably avoided static obstacles using Bug-based navigation
- Achieved 100% flag detection accuracy during testing without observed false positives
- Verified communication between all ROS2 nodes using asynchronous topic-based messaging

<video width="700" controls>
  <source src="/images/Rover Sim.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

## Impact

This project demonstrates the integration of perception, planning, and control into a complete autonomous robotic system. Beyond implementing individual algorithms, the work focused on designing a modular ROS2 architecture capable of coordinating multiple sensing and decision-making components. The resulting framework provides a foundation for future development on physical rover hardware and more advanced autonomous search behaviors.

## Code

Source code and documentation are available on GitHub:

https://github.com/ianspehar99/ROB599_Rover_Search_Project