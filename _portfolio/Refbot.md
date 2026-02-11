---
title: "RefBot"
excerpt: "Automated Video Assisted Referee for Dice Game"
order: 1
collection: portfolio
image: /images/Moneyshot.png
---

### Motivation
My friends and I love playing this game called "Snaps", where you score points by throwing dice high into the air so that they bounce off a table and hit the ground before the other team can catch them. The issue was that this leads to constant arguments about whether a throw was high enough to be legal. Even after putting up a string for reference, it was still hard to judge throws accurately from below. To remove all subjectivity, and save our friendships, I built RefBot, a robot referee designed to autonomously judge throw height.

<img src="/images/Moneyshot.png" alt="Another view of RC Car" style="max-width:400px;">

### System Overview

RefBot uses a fixed camera to track the vertical position of a thrown die relative to a predefined reference line in the camera frame. A Raspberry Pi processes video frames in real time, determines the maximum height reached during a throw, and provides immediate feedback through an LCD screen and RGB LEDs.

**Frame**: 
LEGO Technic and duct tape allowed for rapid prototyping without custom parts. The components are cheap, reusable across projects, and surprisingly strong. They also made it easy to iterate on the design instead of committing to 3D printing, allowing me to focus primarily on software and electronics 

**Camera**: Logitech USB Webcam (≈30 FPS, ~15 FPS under processing load)

I chose a camera as my sensor over other alternatives such as an ultrasonic sensor or LiDAR due to combo of simplicity, speed, and ability to cover a large area

I initially planned to use a Raspberry Pi Camera for its higher FPS and smaller form factor, but I got tired of dealing with ribbon cable connectivity issues, so I switched to the Logitech webcam I had sitting around.  The webcam was readily available and, with adjustments to account for motion blur, proved sufficient for reliable throw detection.

**LCD and LED lights**: Used to indicate the throw outcome. Green lights for good throw, red for bad

**Computer**: Raspberry Pi 4

<div class="grid">
  <img src="/images/raw1.png" alt="">
  <img src="/images/raw2.png" alt="" class="bigger">
  <img src="/images/raw3.png" alt="">
  <img src="/images/dbug1.png" alt="">
  <img src="/images/dbug2.png" alt="" class="bigger">
  <img src="/images/dbug3.png" alt="">
</div>



Captured frames from a successful throw, along with the debugging frames that show the contours and their respective centroids 



Image processing workflow:
- Line up camera so that the horizontal height reference line is at the halfway point in the frame. 
- Run camera at max fps (about 15 when code is running) to capture the dice throw
- Search each frame for white contours (this works becasue of the black backdrop, gets rid of noise)
- Approximate throw height using the average of the contour’s centroid and the topmost pixel (to find balance between noise from motion blur while also trying to get the highest point the die reached), save height
- If no contours are found for a certain number of frames in a row, assume the throw has completed, go back and get the max height value
- Get score using (max height) - (reference line), then convert the pixel value to inches
    - If the score is negative, print it along with a bad message, lights go red. 
    - If the score is psotive, print with a good message, lights go green
- Clear all logged heights and wait for next throw

<img src="/images/LCDOUTPUT.png" alt="Good throw message" style="max-width:400px;">


### Difficulties
As with any robotics project, especially one where you are bringing it from idea to actually using it for something, there were a lot of difficulties to vercome

**Hardware:** 

The Pi camera stopped working (used for FPS/small), ordered new one still stopped working, I think my raspberry pi ribbon cable port is broken. Used cheap USB webcam with lower FPS, but was adequate after code adjustments

**Perception:** 

Lighting and environmental variation made computer vision extremely challenging. Small changes in lighting conditions or surroundings significantly affected performance, especially when using techniques like thresholding, which can be highly sensitive to environmental differences. I ended up having to use a backlight and calibrating the computer vision for a certain time of day.

**Integration:**

Integrating perception, software logic, electronics, and physical hardware is always harder than you expect. Each layer may work independently, but combining them into a single functioning system takes a lot of time and testing. 

**Reliability:**

Robotics highlights the large gap between a proof of concept and a system that works reliably in the real world. Getting something to function correctly 100% of the time - especially under pressure and in front of others - is much harder than demonstrating it in a controlled setting.

This project required a full end-to-end pipeline, from software to electronics to testing and live operation. The first public demo in front of friends was far from smooth: debugging involved pausing the game, inspecting camera frames, and adjusting logic on the fly. While frustrating at the time, it provided valuable lessons about real-world deployment, testing under realistic conditions, and the importance of field testing.


<img src="/images/sheetinback.png" alt="Black background sheet" style="max-width:200px;">
<img src="/images/lightsetup.png" alt="Backlight so the ref can see" style="max-width:200px;">



### Lessons Learned

Definitely not the first time ive learned this lesson, but just relearned the importance of focusing on the most basic functionalities tested and working, and then add more complex features after. My brain always wants to do everything at once, but it gets overwhelming and overly complicated very quickly.


How hard/imperfect motion capture/moving object recognition with computer vision is. Do every thing you can to simplify set up your environemtn for success if possible (black canvas in the background, backlighting)

Learned my lesson to be mindful when following online resources


![](/images/Thirdbest.png)


Overall, this was a highly rewarding project that combined my passion for robotics with solving an actual (extremely minor) problem in my life. It was especially fun to surprise my friends with the system and see their reactions. What stood out most was the real impact it had on the fairness of the game. Whenever there was doubt about a call, we could review the recorded frames, showing everyone exactly what the robot saw. This is essentially a version of the Video-Assisted Referee technology that they use in professional soccer.

Although the robot occasionally made incorrect decisions due to limitations in frame width, reviewing the frames still allowed us to understand the general trajectory of the dice and overrule decisions when necessary. I have never felt more satisfied with a project than after having played for hours without any arguments, and 100% fair games.



<!-- Idea: ArUco pattern??? -->


## Code
Check out the [GitHub repo for this project](https://github.com/ianspehar99/RefBot).