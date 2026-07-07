---
title: "Custom RC Car"
excerpt: "Custom-built RC car with automated maneuvers and crash prevention"
order: 5
collection: portfolio
image: /images/CAR.png
---

Designed, built, and programmed a fully custom remote control car from scratch, including all software, electrical circuitry, mechanical chassis, and steering mechanism. Implemented an embedded control system with automated controller pairing, obstacle detection, and programmable maneuvers including parallel parking and precision turns. The project demonstrates end-to-end mechatronics capability from hardware design through embedded software development.

![RC Car](/images/CAR.png)

### Key Contributions:
- **Designed and assembled** complete electrical circuit including motor drivers, sensors, and microcontroller
- **Built** mechanical chassis and steering mechanism using LEGO Technic and rapid prototyping materials
- **Developed** embedded Python software for motor control, sensor processing, and user input handling
- **Implemented** automated controller pairing and startup sequence
- **Created** custom maneuver library including parallel parking and precision turning routines
- **Integrated** crash deterrence system for obstacle avoidance

### Technologies:
Python · Embedded Systems · Raspberry Pi · Motor Control · Mechatronics · Hardware Design · Rapid Prototyping

### System Architecture:

**Hardware Components**:
- Raspberry Pi 4 for system control and processing
- Motor drivers for precise speed and steering control
- Input receiver for wireless controller communication
- LEGO Technic chassis enabling rapid prototyping and design iteration
- Duct tape construction for quick mechanical assembly

**Software Architecture**:
- Embedded python control loop running on Raspberry Pi
- Input processing pipeline for controller command interpretation
- Motor control algorithms for speed and steering actuation
- Maneuver library with pre-programmed action sequences
- Automated system initialization and controller pairing sequence

### Key Features:

**Automated Operation**: System boots and automatically pairs with the controller, eliminating manual setup steps and enabling immediate operation.

**Crash Deterrence**: Integrated obstacle detection prevents collisions during manual or autonomous operation.

**Custom Maneuvers**: Programmed routines enable complex actions:
- Parallel parking with precision steering control
- Custom turn sequences with specified radii and durations
- Repeatable maneuver execution for testing and demonstration

### Hardware Design:

The vehicle chassis was rapidly prototyped using LEGO Technic components, enabling mechanical iteration without custom fabrication. This approach allowed for quick adjustments to steering geometry and component placement. The electrical system was assembled and integrated with the mechanical platform, with all connections secured for reliable operation.

<img src="/images/car2.png" alt="Another view of RC Car" style="max-width:400px;">

**Design Advantages**:
- Rapid iteration without 3D printing or machining
- Reusable components across multiple projects
- Simple mechanical adjustments during development

### Results:

The RC car successfully operates with:
- **Reliable wireless control** at practical operating ranges
- **Consistent automated pairing** on every startup
- **Accurate maneuver execution** including parallel parking sequences
- **Effective crash prevention** through integrated detection

### Lessons Learned:

- **Hardware-software integration**: Combining electrical, mechanical, and software systems requires careful coordination and testing
- **Rapid prototyping value**: LEGO-based construction enabled mechanical design iterations that would have been time-prohibitive with custom parts
- **Embedded system debugging**: Testing control logic requires structured approaches including serial output and LED indicators
- **Motor control complexity**: Precise speed and steering control requires tuning and calibration for consistent performance

### Code:
[GitHub repository link](https://github.com/ianspehar99/RC-Car)