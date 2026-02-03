---
title: "Mars Rover Auto-Nav Simulation"
excerpt: "Mars Rover Team R&D Project With ROS2 and Gazebo "
order: 2
collection: portfolio
image: /images/Rover.png
---

I built a custom ROS2 and Gazebo simulation for an autonomous rover that searches a cluttered 10 m-radius environment to find a colored flag. I wrote my own navigation node and Bug-based obstacle avoidance algorithm, using proportional control to smoothly steer around obstacles, along with waypoint-driven search behavior. The rover uses Gazebo odometry for localization, LiDAR for obstacle avoidance, and an RGB camera for flag detection. This was an R&D project with the OSU Mars Rover Team to prepare for the autonomous search phase of competitions. 
![Rover Sim](/images/sim_sc.png)





<!-- <img src="/images/car2.png" alt="Another view of RC Car" style="max-width:400px;"> -->
<!-- ADD IN SOME DETAILS FOR THE ROBOTICISTS, CHALLENGES SUCH AS LIDAR WORKAROUND, HOW I DID THE LIDAR / BUG ALGORITHM THE PEOPLE LOOKING AT THIS ARE GOING TO WANT TO SEE SOME TECHNICAL SHIT AND YOULL BE LIT 

+ ADD IN ROS FLEX THAT SHIT BOYYY ROS2 BABY-->

Created an autonomous navigation mode for the rover, allowing it to navigate around obstacles and find a red flag without operator interference.

CHALLENGES -- MENTUON THE TESTIG AND HOW AS YU WORK OUT KINKS AND GET LESS REPRODUCIBLE ERRORS IT GETS MORE DIFFICULT AND FOR THIS PROJECT STOPS BEING WORTH IT

## Code
Check out the [GitHub repo for this project](https://github.com/ianspehar99/ROB599_Rover_Search_Project).