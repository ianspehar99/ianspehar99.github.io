---
title: "SCAPE: Automated Process Control for Laser DED Additive Manufacturing"
excerpt: "Software framework for synchronizing robot motion with real-time process parameter changes during laser directed energy deposition"
order: 1  # Put this first - it's your thesis!
collection: portfolio
image: /images/scape_setup.jpg  # Add a photo of your experimental setup
---
---
title: "SCAPE: Synchronized Process Control for Laser Directed Energy Deposition"
excerpt: "Software framework for automating synchronized robot motion and real-time process parameter changes during laser DED additive manufacturing"
order: 1
collection: portfolio
image: /images/scape_setup.jpg
---

**SCAPE** (Scheduled Control for Automated Parameter Execution) is a software framework I developed for my M.S. thesis that automates synchronized process control for a Kuka-Meltio Laser Directed Energy Deposition (LDED) system. The framework coordinates 6-DOF robot motion with real-time laser power and material feed rate changes at precise physical locations, enabling generation of labeled manufacturing datasets for machine learning research.

### Key Contributions:
- **Designed and implemented** control software architecture in Python
- **Integrated** with KUKA robotic manufacturing platform and Meltio printer
- **Enabled systematic generation** of labeled datasets for ML research
- **Validated** through additive manufacturing trials and statistical analysis
- **Achieved** reliable synchronization with measurable geometric changes

### Technologies:
Python · KUKA Robotics · Meltio 3D Printer · LDED · Motion Control · Manufacturing Automation · Experimental Design · Statistical Analysis

### System Architecture:

**Two-stream coordination**: SCAPE synchronizes (1) 6-DOF KUKA robot motion with (2) laser power and material feed rate changes, triggering parameter updates based on the robot's physical position during printing.

**Data generation**: Logs synchronized position, laser power, and feed rate data at each physical location, enabling labeled dataset creation for process monitoring and ML applications.

### Experimental Validation:
- Designed trials with controlled parameter variations (laser power, feed rate)
- Collected synchronized process data and post-print geometry measurements
- Performed statistical analysis confirming significant geometric changes between process states

### Results:
✅ Reliable synchronization across multiple print trials
✅ Measurable geometric changes corresponding to commanded states
✅ Systematic dataset generation for ML research
✅ Statistically significant process-structure relationships

### Lessons Learned:
- Real-time coordination requires careful timing and communication management
- Industrial integration demands understanding of proprietary protocols
- ML-ready datasets require thoughtful experimental design

### Link to Thesis:
[Add link]

### Code:
[Add link if available]