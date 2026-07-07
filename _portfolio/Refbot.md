---
title: "RefBot: Robot Video-Assisted Referee for Precision Throw Judging"
excerpt: "Real-time computer vision system for throw height verification"
order: 3
collection: portfolio
image: /images/Moneyshot.png
---

Developed a real-time computer vision system that autonomously judges throw height in a dice game, eliminating subjective referee calls. The system uses a fixed camera and Raspberry Pi to track thrown objects against a reference line, providing immediate visual feedback through an LCD screen and RGB LEDs. This project demonstrated the challenges of deploying computer vision in uncontrolled lighting environments and the gap between proof-of-concept and reliable real-world operation.

<img src="/images/Moneyshot.png" alt="Another view of RC Car" style="max-width:400px;">

### Key Contributions:
- **Designed and built** a complete hardware-software system including camera mounting, electronics, and computational hardware
- **Implemented** real-time object tracking using OpenCV contour detection and centroid analysis
- **Developed** a robust height estimation algorithm compensating for motion blur
- **Integrated** user feedback through LCD display and LED indicator system
- **Deployed** and tested the system in live gameplay scenarios

### Technologies:
Python · OpenCV · Raspberry Pi · Computer Vision · Real-Time Systems · Hardware Integration · Embedded Linux

### System Architecture:

**Hardware Setup**: Fixed Logitech USB webcam mounted above the playing area, connected to a Raspberry Pi 4. LEGO Technic frame enabled rapid prototyping and iteration without custom parts. Visual feedback provided through an LCD screen and RGB LEDs mounted on the frame.

**Image Processing Pipeline**:
1. Camera captures frames at ~15 FPS during gameplay
2. Each frame is searched for white contours against a black backdrop (environmental simplification)
3. For each detected contour, throw height is approximated using a weighted average of the contour's centroid and topmost pixel
4. Processing continues until no contours are detected for a configurable number of consecutive frames
5. Maximum height is calculated relative to a predefined reference line and converted from pixels to inches
6. Results are displayed on the LCD with corresponding LED color (green = good throw, red = bad throw)

### Algorithm Design:

The height estimation algorithm balances two competing factors:
- **Motion blur sensitivity**: Using centroid provides stability against noise
- **Peak detection accuracy**: Using topmost pixel captures the true maximum height

The system combines both measurements to approximate throw height while mitigating the impact of motion blur on individual frames. A configurable frame buffer and timeout mechanism handles cases where the die temporarily leaves the camera's field of view during high throws.

<div class="grid">
  <div class="cell"><img src="/images/raw1c.png" alt=""></div>
  <div class="cell"><img src="/images/raw2c.png" alt=""></div>
  <div class="cell"><img src="/images/raw3c.png" alt=""></div>
  <div class="cell"><img src="/images/bug1c.png" alt=""></div>
  <div class="cell"><img src="/images/bug2c.png" alt=""></div>
  <div class="cell"><img src="/images/bug3c.png" alt=""></div>
</div>

### Results:

The system successfully differentiated legal from illegal throws during live gameplay, with post-game frame review enabling verification of close calls. The visual feedback system provided immediate, unambiguous decisions that reduced arguments and improved game fairness.

<img src="/images/LCDOUTPUT.png" alt="Good throw message" style="max-width:400px;">

**Performance Metrics**:
- **Processing rate**: ~15 FPS (sufficient for throw detection)
- **Detection reliability**: Robust under controlled lighting conditions
- **Decision latency**: Real-time feedback (< 1 second per throw)
- **Frame review**: Enabled furthermanual verification of all calls

### Challenges & Solutions:

| Challenge | Solution |
|-----------|----------|
| Raspberry Pi Camera connectivity issues | Switched to USB Logitech webcam for reliability |
| Lighting sensitivity and environment variation | Implemented black backdrop and backlighting; calibrated for specific lighting conditions |
| Motion blur affecting height estimation | Combined centroid and topmost pixel measurements |
| System integration complexity | Focused on basic functionality first; added features incrementally |
| Unreliable deployment in live gameplay | Learned importance of extensive testing under realistic conditions |


<img src="/images/sheetinback.png" alt="Black background sheet" style="max-width:200px;">
<img src="/images/lightsetup.png" alt="Backlight so the ref can see" style="max-width:200px;">

### Lessons Learned:

- **Incremental development**: Testing basic functionality before adding complex features is essential, despite the temptation to implement everything at once
- **Environmental engineering**: Successful computer vision often requires simplifying the environment as much as the algorithm (black backdrop, controlled lighting)
- **Deployment gap**: The difference between a proof-of-concept and a reliable real-world system is substantial and requires extensive testing
- **Robustness priority**: Reliability under pressure (and in front of others) is more important than algorithmic sophistication
- **Integration challenges**: Combining perception, logic, electronics, and hardware into a functioning system requires significantly more time than expected

### Impact:

The system was deployed during live gameplay sessions, demonstrating real-world utility by reducing disputes and ensuring fair play. Frame review capability provided video-assisted referee functionality similar to professional sports systems, allowing players to verify controversial calls post-hoc.

<img src="/images/Secondbest.png" alt="Another view of RC Car" style="max-width:400px;">

### Code:
[GitHub repository link](https://github.com/ianspehar99/RefBot)