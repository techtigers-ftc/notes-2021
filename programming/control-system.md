
# Tech Tigers Control System

## Introduction

 This document will outline our class design and explain how our control system
 will control the robot. 

## Objectives
The objectives of this control system are to:
- Drive the robot
- Control the manipulator ( Arm, Intake, ETC...)
- Allow multiple profiles of the controller inputs, such as different controls to
    drive the robot for each person on the team
- Abstract out the control of different drive systems and different controller
    inputs

This is a good idea because it allows us to change between different input,
drive and manipulator systems without changin the base opmode. It will also prove
beneficial in future years becasue we will be able to reuse much of the code
with a different manupulator.

## Design

