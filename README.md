# Autonomous Rover Control System (ARCS)
A repository for designing and implementing various methods of navigation and control for a rover.


# Outline
Here we detail the goals, methods and deliverables associated with the project
## Goals
* The rover and its various sub-systems will be controllable via a fully Autonomous Rover Control System ([ARCS](https://github.com/GonzagaRobotics/AutonomousRoverControlSystem)). 

* The rover will be capable of maneuvering and driving via the ARCS. 

* The ARCS will utilize environmental information including video stream and sensor data to make decisions. 

* The ARCS will enable the rover to travel to locations given GNSS coordinates for those locations, while avoiding obstacles and taking an efficient and safe route. 

## Methodology
Detailed here is the strategies and technologies we will use to achieve our goals and create the deliverables:
* We will utilize multiple complex models, created in house via various ML techniques, or utilized as pre-trained open-source models, in conjunction with rule-based control and other path-finding methods to create a system that can navigate and control the rover, which we call ARCS. 

* We will deploy this system to the rover’s NVIDIA Jetson TX2, where all models and programs for autonomous control will run. 

* We will utilize a Simulation of the rover to train and test this system. 

* In general, the system will work as follows: 

    - The ARCS will receive its own position in GNSS coordinates from onboard sensors collecting such data 

    - The ARCS will use ROS2 to send commands to the rovers embedded systems to control the motors individually. 

    - ARCS will orient the rover towards the GNSS coordinates of the target point given in the competition by determining the relative position of the target point to itself. 

    - ARCS will send commands over ROS2 to control each driving motor to move directly towards the target point’s position. 

    - ARCS will utilize its various complex models, including models for Computer Vision (CV), to analyze the terrain and the motion of the rover as it moves towards the target so that it can send commands to avoid obstacles and remain stable as it moves. 

      * If an obstacle is detected, its location will be determined and a preliminary path will be calculated to avoid it, which will update as the rover moves around the obstacle. 

## Deliverables
* An Autonomous Control System (ARCS) that can move the rover to a GNSS location, while moving across difficult terrain and avoiding obstacles. 

* The ARCS will be able to utilize environmental information to accomplish this task. 

* The ARCS will communicate with the rover remotely and over ROS2. 

## References
* Deep Object Pose Estimation - ROS Inference: https://github.com/NVlabs/Deep_Object_Pose 
* Particle Filter ROS like (to help navigation): https://github.com/mit-racecar/particle_filter
* Arm Manipulation: http://wiki.ros.org/robotican/Tutorials/Arm%20manipulation
* Reinforcement Learning with ROS and Gazebo: https://github.com/vmayoral/basic_reinforcement_learning/blob/master/tutorial7/README.md
* Motion planning like: https://moveit.ros.org/ or https://navigation.ros.org/
* Control systems: https://control.ros.org/master/index.html

