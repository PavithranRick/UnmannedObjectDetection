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

## Contribution and Methodology
The time taken in the work [1] by three detector models - long term, medium term and short term is directly proportional to the number of models used and it results in 8 different states in a finite state machine. The proposed work reduces the model to two detectors, short and long term detectors, thus improving the performance and reducing the number of states in FSM to identify static foreground objects without losing much of its accuracy. The unmanned object detection system starts by identifying a candidate static foreground region and then to analyse the region for unmanned object. 

Identifying a static object is difficult as there may be many objects surrounding an object that has changes its state from a moving to static object which is the main area of interest. The steps involved in identifying the static foreground object are shown in Figure 1. After selecting the region of interest the input video is fed into two background models namely Short and Long Learning models with different learning rates which learn the background at different updation rates. The result of these models are subsequently passed through a Finite State Machine the result of which shows whether there is any candidate static object or not. The states of the Finite State Machine represent the different states of the object at each stage.

## Implementation details 
### Region of interest selection
In a typical surveillance video without pre-processing there may be lots of unwanted spaces which also comes under the processing area of the algorithm. The algorithms generally capture every pixel in the video and do analysis even if there is no useful information available. In order to avoid this overhead the video is analysed only for selective regions as per the interest. For example, a surveillance camera placed in a no parking area may also cover the roads nearby which may cause unwanted overhead in the algorithm identifying the objects. This can be avoided by selecting only the no parking area and monitoring it. Given the input video four points are selected in the order of the shape required for the ROI. The region is formed by joining the points selected by the user in the direction specified. For example, in order to make a rectangle as the ROI the top left and right corners followed by bottom right and bottom left are made in order to from the ROI. Selecting the ROI reduces the overhead and also the memory and time costs.

The PETS 2006 dataset is taken as the input and fed into the algorithm. The first step is selecting the region of interest for efficient usage of algorithm. The first step consists of a ROI setting window shown in Figure 2. The corresponding shape of the ROI mask region chosen and the points selected are shown in Figure <>. These are the points that are joined together to form the ROI.

### Presentation Slides & Video

In the video, you can see project ideas in action.
<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/MqlWyAuMOZQ" frameborder="0" allow="accelerometer; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</p>
