---
title: "Mars Rover Autonomous Navigation"
excerpt: "Mars Rover Team R&D Project With ROS2 and Gazebo "
order: 2
collection: portfolio
image: /images/Rover.pngw
---

I built a custom ROS2 - Gazebo simulation pipeline for an autonomous rover that searches a cluttered 10 m-radius environment to find a colored flag. I wrote my own navigation node and Bug-based obstacle avoidance algorithm, using proportional control to steer around obstacles, along with a waypoint-driven search pattern. The rover uses Gazebo odometry for localization, LiDAR for obstacle avoidance, and an RGB camera for flag detection. This was an R&D project with the OSU Mars Rover Team to prepare for the autonomous search phase of competitions. 

![Rover Sim](/images/sim_sc.png)


### System Description:


![Rover Sim](/images/diagram.png)
ROS2 node diagram for the system showing workflow and topics published and received


**Waypoint navigation**: The navigation node iterates through a list of waypoints as it reaches each one, calculating the new heading each time and steering the rover in the new direction.

**Obstacle avoidance**: The main navigation node subscribes to the LiDAR scan, and the current pose to get around obstacles. When the front-facing scan readout is below 2.5 meters, the robot stops, turns 90 degrees to the right, and enters “bug mode” to go around the obstacle. It then starts tracking the left-side LiDAR scan distance, turning proportionally to the changes in that reading from the initial stopping distance, to try and stay hugging the wall of the obstacle. If 15 out of the last 20 left-side scans are equal to the max range, the rover assumes that there was a corner to the obstacle that was unable to be followed by the proportional steering, and that it needs to turn 90 degrees to the left. The rover continues this loop until it is back on the m-line, meaning it is once again on the same vector (starting point  > current goal waypoint) as it was before it encountered the obstacle. It then exits bug mode, recalculates a new heading towards the waypoint, and continues this process until the flag is found.

![Rover Sim](/images/bugmode.png)

**Flag Detection**: This was done by using CV2 contouring on the Gazebo RGB camera outputs, looking for sufficiently large red objects in the frame that would indicate that the flag is ahead. If a flag was seen in 4 out of the last 5 images, it sends a message to the main nav node to stop the rover because the flag has been found. 

![Rover Sim](/images/flagcam.png)
Camera view

**Results**: Sequential waypoint navigation worked, with the rover being able to calculate the heading and turn to the next waypoint. Obstacle navigation using LiDAR was also mostly effective and fairly consistent. The proportional following definitely needed some more tuning, and it did have a few failures, but they were rare enough to where it was difficult to recreate the issue for debugging. With more time, it shouldn’t be too hard to iron out any exceptions/bugs. Flag detection using the camera also worked perfectly. 

### Rover in Action!
<video width="600" controls>
  <source src="/images/Rover Sim.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>


## Challenges Faced: 
Subscribing to Gazebo’s Odometry info caused the simulation rover’s location to drift, so that the GUI did not match up with the reported pose. Unfortunately, I was unable to find documentation on how to convert the absolute simulation pose to ROS. Having noisy measurements like this is technically more accurate, but for testing and debugging original algorithms, it was pretty terrible. The real life rover will also have a Kalman filter, which will make it more accurate. 

I could not get the Gazebo LiDAR sensor implementation to work at all, even when trying the example code on Gazebo’s website, so I ended up having to fake it. I did this using a separate node which took in the locations of the rover and the simulated obstacles as inputs, and published LaserScan messages that mimicked what a working LiDAR would be able to see from the robot's current position.


### Lessons Learned: 
- Autonomous robot movement control in ROS is difficult because everything is looping and you don’t want to block your code. Lots of while loop checking and boolean flags

- How to set up a Gazebo sim/ROS bridge

- Should have started working on the simulation sooner, as that changed some of the ways that I approached things. I think I did do a good job of starting it early on, but in the future the first thing I would do is make sure I could get the robot moving and the sensors working properly

- Importance of modularity/breaking into multiple nodes and testing independently. I’ve been bad about this is the past, because it seems like more work at first, but I was fairly disciplined during this project and it made things so much easier

- As previously mentioned, the closer you get to it working flawlessly, the harder it is to reproduce criticial errors for debugging. It got to the point where it stopped being worth it 






<!-- <img src="/images/car2.png" alt="Another view of RC Car" style="max-width:400px;"> -->
<!-- ADD IN SOME DETAILS FOR THE ROBOTICISTS, CHALLENGES SUCH AS LIDAR WORKAROUND, HOW I DID THE LIDAR / BUG ALGORITHM THE PEOPLE LOOKING AT THIS ARE GOING TO WANT TO SEE SOME TECHNICAL SHIT AND YOULL BE LIT 

+ ADD IN ROS FLEX THAT SHIT BOYYY ROS2 BABY-->



## Code
Check out the [GitHub repo for this project](https://github.com/ianspehar99/ROB599_Rover_Search_Project).