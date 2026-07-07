---
title: "RefBot: Video-Assisted Referee for Precision Throw Judging"
excerpt: "Real-time computer vision system for autonomous throw height verification"
order: 3
collection: portfolio
image: /images/Moneyshot.png
---

RefBot is a computer vision system I developed to automate throw height judging in a dice game, eliminating subjective referee decisions. Using a Raspberry Pi, USB camera, and OpenCV, the system tracks thrown objects relative to a reference line and provides immediate visual feedback through an LCD display and RGB LEDs. The project emphasized robust real-time vision, hardware integration, and the practical challenges of deploying computer vision in an unpredictable environment. 

<img src="/images/Moneyshot.png" alt="RefBot system" style="max-width:700px;">

## Highlights

- Designed and built a complete computer vision system using Raspberry Pi and OpenCV
- Developed a real-time object tracking algorithm based on contour detection and centroid analysis
- Created a height estimation method combining centroid and peak detection to compensate for motion blur
- Integrated LCD and RGB LED feedback for immediate height judgement indication
- Deployed and evaluated the system during live gameplay

## Technical Stack

**Software:** Python · OpenCV · Raspberry Pi OS  
**Hardware:** Raspberry Pi 4 · Logitech USB Camera · LCD Display · RGB LEDs  
**Methods:** Computer Vision · Contour Detection · Embedded Systems · Real-Time Image Processing

## Results & Validation

<table>
<tr>
<td align="center" width="50%">

<img src="/images/LCDOUTPUT.png" alt="LCD Output" style="max-width:100%;">

**1. Real-Time Decision Feedback**

Throw height was calculated in real time and immediately displayed on the LCD while RGB LEDs provided clear visual pass/fail feedback.

</td>

<td align="center" width="50%">

<img src="/images/Secondbest.png" alt="Gameplay" style="max-width:100%;">

**2. Live System Deployment**

The complete hardware system was successfully deployed during gameplay, demonstrating autonomous referee functionality.

</td>
</tr>
</table>


**3. Computer Vision Pipeline**

The image processing algorithm detected object contours, estimated throw height relative to a calibrated reference line, and combined centroid and peak measurements to improve robustness against motion blur.

<div class="grid">
  <div class="cell"><img src="/images/raw1c.png" alt=""></div>
  <div class="cell"><img src="/images/raw2c.png" alt=""></div>
  <div class="cell"><img src="/images/raw3c.png" alt=""></div>
  <div class="cell"><img src="/images/bug1c.png" alt=""></div>
  <div class="cell"><img src="/images/bug2c.png" alt=""></div>
  <div class="cell"><img src="/images/bug3c.png" alt=""></div>
</div>

## Impact

RefBot demonstrates the integration of embedded computing, computer vision, and hardware design into a complete real-time system. Beyond implementing object detection, the project highlighted the importance of environmental engineering, including controlled lighting and background design for reliable computer vision deployment in real world conditions. The resulting system successfully reduced subjective referee decisions while providing immediate visual feedback and post-game verification.

## Code

Source code and documentation are available on GitHub:

https://github.com/ianspehar99/RefBot




