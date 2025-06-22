---
title: "Ball Tracking Robot Arm"
excerpt: "(Robotics, Software) Four dofs robot built and programmed to track balls + other objects<br/><img src='/images/500x300.png'>"
collection: portfolio
---

[Software Architecture and Implementation](https://ritalij.github.io/files/me008_softwarearchitectureimplementation.pdf)

The objective of the system is to control two motors based on user-controlled events, specifically, to control the motion of the robot (two degrees of freedom) based on key controls. We also want to ensure that the robot moves as quickly as possible (under its max velocity) as well as smoothly.
The system must move smoothly (continuous position and velocity), thus requiring the usage of splines to control the motion from one position to a goal position. We used cubic splines to define the parameters for our trajectories. The motor changes its position in a discrete fashion at time intervals of 0.01 s. The motor is user-controlled and must move to a specified location with keystrokes. We want our code to be error-prone (for example, undefined keys should not affect the behavior). Since we are also requiring smooth motions, our system must be able to change its motion in response to an event in the middle of a different motion.
Our software principles were to maintain the compactness and intuition of the code. Specifically, we organized our initialization, event-handling, and other components of the code to flow naturally and be readable, for example, by utilizing clear variable names. We also focused heavily on generalizability to ensure that our code is easy to refactor. We defined reusable functions for parameter computations, and we also relied on lists and condensing the code into vector operations using Numpy. This ensures a cleaner codespace, as there are fewer variables to keep track of, while still allowing us to control multiple degrees of freedom of the robot.	

[Object Detector and Performance](https://ritalij.github.io/files/me008_objectdetectorperformance.pdf)

The objective of this detector is to detect a blue ball within a certain color range, display its binary image, and draw a contour around its shape in a BGR (blue green red) image. To do this, we first altered the camera’s brightness and exposure settings to see a clearer image. We then created a crosshair on the BGR image, placed the blue ball in the center of the frame, and detected the center pixel’s HSV values that correspond to the blue color we desired. When using this detector, the user should expect to see two images: a BGR image and a binary image. In the BGR image, green contours are drawn around any blue object over a certain area in the HSV values we previously specified, while red contours are drawn for smaller objects. 

[Mechanical Design and Fabrication](https://ritalij.github.io/files/me008_mechanicaldesignfabrication.pdf)

The assembled robot consists of two motors (one for panning and one for tilting), a camera, and two L-brackets that were 3D printed.

