#**Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**




* Make a pipeline that finds lane lines on the road
* Apply this to static images to prove the algorithm 


* Lane detection is one of the most critical parts of a self-driving vehicle. In this project we use openCV, numPy, Matplotlib and MoviePy to draw lines on the video stream given in the assignment. To do that we develop pipeline of steps and each step is chained to the next to get the final output where lanes on either side of the vehicle will be highlighted with tick red lines to mark the path for the car to take. One we get this to work with the test images, the pipeline is extended to process a full test video. 

* Road condition: The input is video and assumption is it is taken from a camera mounted on the dashboard. The car is driven on a straight road (without curves) that the images on a straight road. 
    It is daytime with sunny weather.

* The projects works well with the     


* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
