# Tech Tigers Control System

## Introduction

 This document describes the software design of the control system.

## Objectives
The objectives of this control system are to:
- Drive the robot
- Control the manipulator ( Arm, Intake, ETC...)
- Make the code modular
- Abstract out the control of different drive systems and different controller
    inputs

Making the code modular is helpful because it makes the code easy to manage. It
also allows us to use interchangeable components, so we can mix and match each
time. Finally, it makes our opmodes shorter and easier to write.

## Design

In our design, we have 3 types of modules.
- **Controllers** use inputs from the game controller in order to calculate
  inputs that are used in the Driver and Manipulator modules.
- **Drivers** takes inputs from the Controller and uses them to make the robot
  drive in certain ways.
- **Manipulators** takes inputs from the Controller and uses them to cantrol
  one or more manipulators on the robot.

Here is a diagram of our design:

![Class-Design-Diagram](/images/class-design-diagram.png)

## Notes
- Having multiple Controller implementations allows us to have different
  control schemes for different drivers; we will only implement as needed.
- These modules can be reused over different seasons
