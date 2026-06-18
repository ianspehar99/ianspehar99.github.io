---
title: "Autonomous Rover Navigation for Search & Rescue Competitions"
excerpt: "ROS2-based autonomous rover with custom obstacle avoidance and vision-based target detection"
order: 2
collection: portfolio
image: /images/Rover.png
---

Developed a ROS2-Gazebo simulation pipeline for an autonomous rover capable of navigating cluttered environments and detecting colored targets. Implemented custom navigation algorithms including a Bug-based obstacle avoidance strategy and vision-based flag detection using OpenCV contouring. The system was developed as an R&D project for the OSU Mars Rover Team to prepare for the autonomous search phase of international competitions.

### Key Contributions:
- **Architected** a modular ROS2 system with three primary nodes: navigation, obstacle avoidance, and vision detection
- **Designed and implemented** a Bug-based obstacle avoidance algorithm using LiDAR data
- **Developed** vision-based flag detection using OpenCV contouring with temporal confirmation
- **Created** a custom LiDAR simulation workaround when the Gazebo sensor implementation proved non-functional
- **Integrated** waypoint-driven search patterns with dynamic obstacle response

### Technologies:
ROS2 · Python · Gazebo · LiDAR · OpenCV · Odometry · Bug Algorithm · Proportional Control · Contour Detection

### System Architecture:

[Keep your existing node diagram - it's excellent!]

**Navigation Pipeline**: The main navigation node iterates through predefined waypoints, calculating headings and steering the rover using proportional control. The system continuously monitors LiDAR data to detect obstacles while progressing toward the current target waypoint.

**Obstacle Avoidance**: The custom Bug-based algorithm triggers when forward-facing LiDAR readings fall below 2.5 meters. The rover:
1. Stops and turns 90° right to enter "Bug Mode"
2. Tracks left-side LiDAR distance, applying proportional steering to maintain wall contact
3. Detects corners when 15 of 20 left-side scans show max range, triggering a 90° left turn
4. Exits Bug Mode upon returning to the original line-of-sight vector toward the waypoint

[Keep your Bug Mode diagram]

**Vision-Based Detection**: An OpenCV pipeline processes Gazebo RGB camera outputs, applying contouring to identify sufficiently large red objects. Detection requires 4 out of 5 consecutive positive frames to reduce false positives before signaling the navigation node to stop.

[Keep your camera view images]

### Simulation Validation:

[Keep your simulation video]

The system was validated entirely in Gazebo simulation due to hardware availability constraints. Sequential waypoint navigation performed reliably, with the rover successfully calculating headings and executing turns. The Bug-based obstacle avoidance demonstrated consistent effectiveness, with failures rare enough to impede comprehensive debugging.

### Results:
- **Waypoint navigation**: Successfully executed multi-waypoint paths with accurate heading calculations
- **Obstacle avoidance**: Bug algorithm effectively navigated around obstacles in most scenarios
- **Flag detection**: Achieved 100% detection accuracy with no false positives using temporal confirmation
- **System integration**: All ROS2 nodes successfully communicated through the defined topic architecture

### Challenges & Solutions:

| Challenge | Solution |
|-----------|----------|
| Gazebo odometry drift between simulation and published pose | Documented as realistic sensor noise; future implementation will include Kalman filter for improved state estimation |
| Non-functional Gazebo LiDAR sensor | Developed custom LiDAR simulation node that publishes LaserScan messages based on obstacle locations relative to rover pose |
| Difficult-to-reproduce rare failures in Bug algorithm | Acknowledged limitation; further tuning required for edge-case handling |

### Lessons Learned:
- **Asynchronous control design**: Autonomous navigation in ROS2 requires careful state management with flags and non-blocking loops to prevent code stalling
- **Early simulation integration**: Establishing Gazebo-ROS2 communication and sensor validation should be the first step in future projects
- **Modular architecture**: Breaking functionality into separate nodes with independent testing dramatically simplified debugging
- **Diminishing returns**: Once a system achieves near-perfect performance, edge-case failures become exponentially harder to reproduce and debug

[Keep your video]



<!-- <img src="/images/car2.png" alt="Another view of RC Car" style="max-width:400px;"> -->
<!-- ADD IN SOME DETAILS FOR THE ROBOTICISTS, CHALLENGES SUCH AS LIDAR WORKAROUND, HOW I DID THE LIDAR / BUG ALGORITHM THE PEOPLE LOOKING AT THIS ARE GOING TO WANT TO SEE SOME TECHNICAL SHIT AND YOULL BE LIT 

+ ADD IN ROS FLEX THAT SHIT BOYYY ROS2 BABY-->



## Code
Check out the [GitHub repo for this project](https://github.com/ianspehar99/ROB599_Rover_Search_Project).