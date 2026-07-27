---
title: "SCAPE: Automated Framework for LDED Machine Learning Dataset Generation"
excerpt: "M.S. thesis on automated parameter control of robotic metal additive manufacturing"
order: 1
collection: portfolio
image: /images/thesis/SCAPE pic.png
---

**SCAPE** (Scheduled Control for Automated Parameter Execution) is the software framework I developed for my M.S. thesis to automate synchronized process control on a KUKA–Meltio Laser Directed Energy Deposition (LDED) system. LDED printing depends on precisely coordinating three variables — robot travel speed, laser power, and wire feed rate — but travel speed lives inside the robot's own motion program while power and feed rate are set independently through the printhead interface. The hardware had no native way to keep these in sync, which meant every parameter change during a print had to be manually timed and manually logged, making systematic experimentation slow and error-prone.

I designed SCAPE to close that gap: it automatically generates and modifies KUKA motion programs, schedules parameter changes to specific physical locations along the toolpath, and drives the printhead interface directly to execute those changes in sync with the robot's motion — all while logging everything needed to reconstruct exactly what happened, where. The result is a system that turns a manual, one-off experimental process into an automated, repeatable pipeline for generating high-quality, labeled datasets for additive manufacturing machine learning research.

<img src="/images/thesis/kukameltio.png" alt="KUKA-Meltio LDED system" style="max-width:700px;">
Highlights
Designed and implemented a Python automation framework for robotic metal additive manufacturing, synchronizing KUKA robot motion — including travel speed defined in the motion program — with externally controlled laser power and wire feed rate
Developed algorithms to automatically generate and modify KUKA robot motion programs across varying toolpath patterns, paired with synchronized parameter schedules for systematic process-variable data collection
Built timing compensation and resynchronization methods to correct for machine latency between robot motion and external parameter entry, preventing cumulative drift over long autonomous builds
Automated parameter entry through the printhead interface using PyAutoGUI, executing scheduled changes to within 0.05 seconds of planned timing
Automated logging of robot position, travel speed, laser power, and feed rate in real time, correlating each parameter state to its exact print location for labeled dataset generation
Experimentally validated synchronization accuracy through additive manufacturing trials and statistical analysis, confirming sub-millimeter alignment between planned and executed parameter changes
Technical Stack

Software: Python · PyAutoGUI · Automation · Control Algorithms · Data Logging
Hardware: KUKA KR20 Robot · Meltio M450 LDED System
Methods: Experimental Design · Robotic Automation · Timing/Latency Compensation · Statistical Analysis · Machine Learning Dataset Generation

Results & Validation
<table> <tr> <td align="center" width="50%"> <img src="/images/thesis/map.png" alt="Parameter Map" style="max-width:100%;">
Planned Parameter Schedule

Generated synchronized parameter maps defining where laser power and feed rate changes should occur during printing.

</td> <td align="center" width="50%"> <img src="/images/thesis/print.png" alt="Printed Part" style="max-width:100%;">
Resulting Print

SCAPE executed parameter changes at the intended locations, producing visible geometric differences along the print pattern.

</td> </tr> </table> <div align="center"> <img src="/images/thesis/topo.png" alt="Topography Validation" style="max-width:850px; width:100%;">
Experimental Validation

3D surface scans confirmed that the resulting geometry matched the planned parameter schedule, validating synchronization accuracy within ~0.5 mm — with parameter entry timing accurate to within 0.05 seconds of the planned schedule.

</div>
Impact

SCAPE transforms a manual, hand-timed experimental workflow into a fully automated, repeatable pipeline for generating high-quality labeled datasets for machine learning training — eliminating a major bottleneck in collecting the volume and consistency of data that ML models need. By solving the underlying synchronization problem between a robot's internal motion program and externally controlled process parameters, the framework serves as the foundation for future ML-based closed-loop monitoring and autonomous process control in LDED, with the underlying approach generalizable to other robotic manufacturing platforms facing similar multi-system coordination challenges.

Thesis

Paper currently under peer review.

Code

Source code and documentation are available on GitHub:

https://github.com/ianspehar99/LDED-ML-Project