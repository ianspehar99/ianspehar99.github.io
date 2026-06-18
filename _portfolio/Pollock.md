---
title: "Pollock: Autonomous Image-to-Painting Robot"
excerpt: "Kinova robot arm that analyzes images and translates them into artistic brush stroke paintings"
order: 4
collection: portfolio
image: /images/pollockms.png
---

Developed the core algorithmic pipeline for an autonomous painting robot that analyzes input images and translates them into artistic interpretations using a Kinova robot arm. The system processes visual data through contour detection and path planning to generate sequential brush stroke commands, producing physical paintings that resemble the original source images.

### Key Contributions:
- **Designed and implemented** the complete image-to-command pipeline for robotic painting
- **Developed** contour detection and point condensation algorithms for image simplification
- **Created** advanced pathing logic for sequenced brush stroke generation
- **Integrated** brush stroke command generation for Kinova robot execution

### Technologies:
Python · OpenCV · Kinova Robotics · Computer Vision · Path Planning · Image Processing · Robotics · Brush Stroke Generation

### System Architecture:

**Image Processing Pipeline**:
1. Input image is loaded and preprocessed for contour detection
2. OpenCV contour detection identifies shape boundaries and regions
3. Contours are condensed into representative points for stroke generation
4. Advanced pathing logic determines the optimal sequence of strokes
5. Brush stroke commands are generated and formatted for the Kinova robot

**Command Generation**: The system translates visual features into robotic motion commands, determining:
- Stroke start and end positions
- Stroke direction and curvature
- Brush pressure and paint application timing
- Stroke order for visual coherence

### Key Features:

**Contour-Based Interpretation**: Images are processed by identifying meaningful contours that capture the essence of the subject, condensing them into a manageable set of points for robotic execution.

**Intelligent Path Planning**: The algorithm sequences brush strokes to create a coherent painting, optimizing the order of strokes to minimize robot repositioning while maintaining artistic integrity.

**Artistic Translation**: The system balances faithful representation with artistic interpretation, producing paintings that recognize the subject while embracing the robotic aesthetic.

### Results:

The system successfully generates paintings that:
- **Recognizably depict** the original source images
- **Demonstrate** coherent artistic composition
- **Showcase** the robot's ability to translate visual data into physical art
- **Produce** consistent results across varied input images

[Keep your before/after images showing source images and resulting paintings]

**Example Outputs**:
- [Your horse images - keep them, they're great evidence!]
- Source: scuffedhorse.png → Final painting showing contour-based interpretation
- K-means processing for color segmentation and stroke planning

### Challenges & Solutions:

| Challenge | Solution |
|-----------|----------|
| Converting image data to robotic motion | Implemented contour detection and point condensation pipeline |
| Stroke sequencing for coherent art | Developed advanced pathing logic with visual coherence optimization |
| Balancing representation with interpretation | Designed artistic translation parameters allowing adjustable abstraction levels |

### Future Improvements:

- **Color processing**: Implementing color segmentation for multi-color paintings
- **Stroke variation**: Adding brush width, pressure, and angle variation
- **Layered painting**: Supporting multiple passes for depth and texture

### Code:
[GitHub repository link - add if available]

[Keep your demo images and videos]