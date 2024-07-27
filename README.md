[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/5mCoF9-h)
# TOBB ETÜ ELE495 - Capstone Project

# Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [System Explanation](#system-explanation)
- [Installation](#installation)
- [Usage](#usage)
- [Screenshots](#screenshots)
- [Acknowledgements](#acknowledgements)

## Introduction
In this project we developed a system, which Works on Jetbot, can automatically parks itself to assigned park station. <u>A fully autonomous system (not using any sensors for detecting or for any other needs)</u> tries avoiding parking lines while parking. When it gets into the parking lot it automatically stops and gives information about its status and if it’s violated any rules (crossed parking line). In this Project we are aiming to demonstrate that fully autonomous parking is applicable.

## Features
1. Hardware: 
*We are using;
*Nvidia jetson nano to control the system.
*JETBOT package for movement and IMX219 for imaging.
*HC-05 Bluetooth module for communication with phone applications.

2. Operating System and packages:
As an operating system we are using Linux ubuntu (default Jetson nano operating systems) and for packages we are using default system packages that comes with Jetbot image installation only one additional package for communication pyserial. You can follow the steps on this site to download it. https://github.com/pyserial/pyserial

3. Applications:
We used only MIT app converter for creating user-interface for our project application. In the application people can select the parking lot they want to use and then they can start the process. Application will give information about if it can park or not and if it violated any rules (crossing parking line).


## System Explanation: 
Our system uses Resnet18 for road following. We trained the model with 350 images. After training Jetbot could follow the line in the middle of the platform. 
After following the road our model looks around to see parking lots. At this point it uses Alexnet for number detection. It calculates a percentage for each number. If the percentage for the parking lot that has been chosen higher than %80 percent, it starts parking process. 
For parking we are using Alexnet we are creating a model for each parking lot. In each model system decides if it should go right, left, straight or it should stop.  We trained all the models with 2400 images. After training, model could park itself without crossing parking lines. 


## Installation
Describe the steps required to install and set up the project. Include any prerequisites, dependencies, and commands needed to get the project running.

```bash
# Example commands
git clone https://github.com/username/project-name.git
cd project-name
```

## Usage
Provide instructions and examples on how to use the project. Include code snippets or screenshots where applicable.

## Screenshots
Include screenshots of the project in action to give a visual representation of its functionality. You can also add videos of running project to YouTube and give a reference to it here. 
![image](https://github.com/user-attachments/assets/9e560841-ebfc-49a9-a548-251b6f37c3e5)

## Acknowledgements
Give credit to those who have contributed to the project or provided inspiration. Include links to any resources or tools used in the project.

[jetbot official repository](https://github.com/NVIDIA-AI-IOT/jetbot)\
[jetson hacks](https://jetsonhacks.com/)\
[nvidia developer forum](https://forums.developer.nvidia.com/)\
and jetbot image default notebooks

