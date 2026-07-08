---
title: "SCAPE: Automated Framework for LDED Machine Learning Dataset Generation"
excerpt: "M.S. thesis on automated parameter control of robotic metal additive manufacturing"
order: 1
collection: portfolio
image: /images/thesis/SCAPE pic.png
---

**SCAPE** (Scheduled Control for Automated Parameter Execution) is the software framework I developed for my M.S. thesis to automate synchronized process control on a KUKA–Meltio Laser Directed Energy Deposition (LDED) system. Because the hardware could not natively coordinate robot motion with laser power and wire feed rate changes, I designed a scheduling and synchronization framework that executes parameter updates at precise physical locations during printing. The system enables automated generation of efficient and high quality machine-learning-ready datasets for additive manufacturing research.


<img src="/images/thesis/kukameltio.png" alt="KUKA-Meltio LDED system" style="max-width:700px;">

## Highlights

- Designed and implemented a Python automation framework for robotic metal additive manufacturing
- Developed algorithms to automatically modify KUKA robot programs and generate synchronized parameter schedules
- Created timing compensation and resynchronization methods to overcome machine latency and prevent cumulative timing drift
- Automated logging of robot position, travel speed, laser power, and feed rate for labeled dataset generation
- Experimentally validated synchronization accuracy through additive manufacturing trials and statistical analysis

## Technical Stack

**Software:** Python · Automation · Control Algorithms · Data Logging  
**Hardware:** KUKA KR20 Robot · Meltio M450 LDED System  
**Methods:** Experimental Design · Robotic Automation · Statistical Analysis · Machine Learning Dataset Generation

## Results & Validation

<table>
<tr>
<td align="center" width="50%">

<img src="/images/thesis/map.png" alt="Parameter Map" style="max-width:100%;">

1. Planned Parameter Schedule

Generated synchronized parameter maps defining where laser power and feed rate changes should occur during printing.

</td>

<td align="center" width="50%">

<img src="/images/thesis/print.png" alt="Printed Part" style="max-width:100%;">

2. Resulting Print

SCAPE executed parameter changes at the intended locations, producing visible geometric differences along the print pattern.

</td>
</tr>
</table>

<div align="center">

<img src="/images/thesis/topo.png" alt="Topography Validation" style="max-width:850px; width:100%;">

3. Experimental Validation

3D surface scans confirmed that the resulting geometry matched the planned parameter schedule, validating synchronization accuracy within ~ 0.5 mm.

</div>

## Impact

SCAPE transforms a manual experimental workflow into an automated, repeatable pipeline for generating high-quality labeled datasets for machine learning training. The framework serves as the foundation for future ML-based closed-loop monitoring and autonomous process control in LDED.

## Thesis

**Paper currently under peer review.**

## Code

Source code and documentation are available on GitHub:

https://github.com/ianspehar99/LDED-ML-Project