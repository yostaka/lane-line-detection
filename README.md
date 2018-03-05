# **Finding Lane Lines on the Road** 

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project the code detects lane lines in images using Python and OpenCV.  OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.  

The contents of this repository is built based on Udacity Self-Driving Car Engineer Nanodegree Program. For more details, please refer to the following links:
https://www.udacity.com
https://github.com/udacity/CarND-LaneLines-P1

Prerequisite
---
Jupyter Notebook, Python 3 and several packages need to be installed to run the code in this repository. For more details, please refer to https://github.com/udacity/CarND-LaneLines-P1.

How to run
---
Open the code(P1.ipynb) from Jupyter notebook and run

Limitations
---
Followings are potential shortcomings (limitations) with the pipeline:
* when lane lines are not straight lines. In that case, annotated lines would not be aligned with actual lane lines.
* when lane lines length are too short. In that case, annotated lines would not be shown because the pipeline would not identify the lines.
* when horizon line location is changed, the line annotation would not be shown correctly. That might happens when camera angle is changed, or when the car drives on a road with slope.
