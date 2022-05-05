# Unmanned Object Detection

## Project Resources 

### Project Proposal [Link to the project proposal](./assets/CV_proposal.pdf)

### Midterm Report [Link to the midterm report](./assets/CV_midterm_report.pdf)


## Introduction:

Detecting an object that has been carried by a human into the scene and suddenly left unattended  is an important problem in visual surveillance research. Since the spectrum of suspicious objects is  broad, we can use general purpose object detection algorithms to identify these objects in the scene. . 

We have developed a system that initially detects the static foreground objects and then analyzes the back-traced trajectories of object owners to decide whether the object is left unattended or not. 

<p align="center">
<img width="800" src="https://raw.githubusercontent.com/PavithranRick/UnmannedObjectDetection/gh-pages/assets/001.png">
</p>


## Motivation:

In public places like railway stations, airports there may be scenarios where a person enters a scene with an object, places the object that may be suspicious and leaves the scene after placing the object. There are incidents where a vehicle is parked in a no parking zone. These kinds of objects are difficult to identify in a video scenario as they change from a moving position to a static position. There are many algorithms to find the moving foreground objects and also the objects that are static from the beginning of the scene. The algorithms that detect the objects that change from moving to stationary either do not detect the objects accurately or add more overhead in time and memory. Also, there may occur a scenario where a person places an object accidentally and then returns back to take the object. These kinds of scenarios should not result in an alarm, so it requires a tracking of the owner of the object. After the verification of the owner and if the owner does not return to the object only then the alarm should be raised.

<p align="center">
  <img alt="Light" src="https://raw.githubusercontent.com/PavithranRick/UnmannedObjectDetection/gh-pages/assets/002.png" width="45%" height="250">
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="Dark" src="https://raw.githubusercontent.com/PavithranRick/UnmannedObjectDetection/gh-pages/assets/003.png" width="45%" height="250">
</p>

### Presentation Slides & Video

In the video, you can see project ideas in action.
<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/MqlWyAuMOZQ" frameborder="0" allow="accelerometer; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>