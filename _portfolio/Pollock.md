---
title: "Pollock: The Painting Robot"
excerpt: "Computer vision pipeline that transforms images into robotic paintings"
order: 4
collection: portfolio
image: /images/pollockms.png
---

Pollock is a robotic painting system that transforms input images into physical artwork using a Kinova robotic arm. I developed the complete image-to-command pipeline, converting photographs into sequential brush strokes through computer vision, contour extraction, and path planning. The project demonstrates the integration of perception, motion planning, and robotics to produce artistic interpretations of source images.

<img src="/images/pollockms.png" alt="Pollock Painting Robot" style="max-width:700px;">

## Highlights

- Designed and implemented the complete image-to-command pipeline for robotic painting
- Developed computer vision algorithms for contour extraction and image simplification
- Created path planning algorithm to generate brush stroke sequences
- Generated robot-compatible motion commands for autonomous painting with a Kinova robotic arm
- Optimized stroke ordering to improve painting efficiency while preserving image features

## Technical Stack

**Software:** Python · OpenCV · Image Processing  
**Hardware:** Kinova Robotic Arm  
**Methods:** Computer Vision · Contour Detection · K-Means Clustering · Path Planning

## Results & Validation

<div align="center">

<img src="/images/horse/oghorse.png" alt="Original Horse Drawing" style="max-width:700px; width:100%;">

**1. Source Image**

The system begins with an input image that is processed into representative visual features for robotic reproduction.

<br><br>

<img src="/images/horse/kmeans.png" alt="K-Means Clustering" style="max-width:700px; width:100%;">

**2. Image Segmentation**

K-means clustering simplifies the image into representative regions, reducing visual complexity while preserving important features for stroke generation.

<br><br>

<img src="/images/horse/bonitohorse.png" alt="Full Resolution Path" style="max-width:700px; width:100%;">

**3. High-Resolution Stroke Planning**

The path planning algorithm generated detailed robot trajectories using all extracted points, producing the highest-fidelity digital reconstruction of the horse image.

<br><br>

<img src="/images/horse/scuffedhorse.png" alt="Reduced Resolution Path" style="max-width:700px; width:100%;">

**4. Hardware-Aware Path Simplification**

Because the physical brush width limited achievable detail, the stroke sequence was reduced by sampling fewer points. This produced a lower-resolution trajectory better suited for physical execution.

<br><br>

<img src="/images/horse/final.png" alt="Final Robotic Painting" style="max-width:700px; width:100%;">

**5. Robotic Execution**

The simplified trajectory was executed by the Kinova robot arm, producing a physical painting that preserved the major visual features of the original image.

</div>


## Impact

Pollock demonstrates the integration of computer vision, path planning, and robotic manipulation into a complete autonomous painting system. The project explores how visual information can be transformed into executable robot trajectories while balancing image fidelity with the physical limitations of the robotic end effector. By bridging perception, motion planning, and physical execution, the framework provides a foundation for future applications in robotic drawing, automated art generation, and creative manufacturing.

## Code

Source code and documentation are available on GitHub:

https://github.com/ianspehar99/Pollock