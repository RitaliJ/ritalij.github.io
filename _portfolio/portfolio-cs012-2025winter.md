---
title: "Light-responsive vehicle"
excerpt: "Raspberry Pi Pico vehicle detecting and following light source<br/><img src='/images/500x300.png'>"
collection: portfolio
---

**Technologies**: Raspberry Pi Pico, PWM, Photoresistors, DC Motors, L298N H-Bridge, Breadboarding, MicroPython, 3D Printing

## Overview
This project involved designing, constructing, and programming a light-following robot car using a Raspberry Pi Pico microcontroller. The core objective was to build a reactive robotic system capable of detecting and following a flashlight beam. This was achieved through a combination of photoresistor-based light sensing and motor control via a dual H-Bridge. The project required skills in physical assembly, embedded systems programming, and sensor data processing.

## Learning Outcomes

Through this project, we explored a range of robotics and embedded systems concepts:

### Hardware Fundamentals
- Worked with breadboards, GPIO pins, and safe circuitry practices.
- Connected LEDs, buttons, and potentiometers to build basic reactive systems.
- Understood voltage and current constraints while powering sensors and motors.

### Reactive Systems and Input Processing
- Implemented sensor-based control using buttons, potentiometers, and analog inputs.
- Applied Pulse Width Modulation (PWM) to create nuanced motor behaviors and responsiveness.
- Used photoresistors to detect light intensity and dynamically influence the robot’s motion.

### Actuation and Control
- Explored electric machines, including DC motors and servos.
- Used the L298N dual H-Bridge to control two DC motors independently.
- Created a two-wheeled robot with a caster ball to support steering.

### Peripheral Devices and Integration
- Gained exposure to more advanced peripherals such as IMUs and sound sensors.
- Learned to integrate multiple input sources for richer interaction.
- Investigated how multiple microcontrollers could communicate for advanced control architectures.

## Project Objectives

### Safe Goals
- Assemble a working robot that can respond to commands from the microcontroller.

### Target Goals
- Enable the car to track and follow a flashlight beam by processing light intensity from photoresistors.

### Reach Goals
- Integrate sound sensors to control speed or behavior.
- Add an IMU-based “remote control” using a secondary microcontroller for gesture-based navigation.
- Explore communication protocols between multiple microcontrollers for distributed control.

## Materials

### Mechanical
- Custom chassis (3D printed + sourced from kit)
- 2 wheels + metal caster ball
- 2 DC motors (one per wheel)
- Motor housing and mountings
- Protective casing for microcontroller and wiring

### Electrical
- Raspberry Pi Pico microcontroller
- L298N Dual H-Bridge motor driver
- Breadboard and jumper wires
- Photoresistor sensor(s)
- Power supply or battery pack

## Software
- Programming language: MicroPython
- Data processing for light sensors
- PWM-based motor control
- Logic for steering decisions based on light intensity comparison

---

This project provided a hands-on introduction to real-world robotics and embedded programming, reinforcing both theoretical and practical knowledge of sensors, control systems, and microcontroller-based design.
