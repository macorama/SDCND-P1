#**Finding Lane Lines on the Road** 

---

##**Goals** 


*   Lane detection is one of the most critical parts of a self-driving vehicle. In this project we use openCV, numPy, Matplotlib and MoviePy to draw lines on the video stream given in the assignment. To do that we develop pipeline of steps and each step is chained to the next to get the final output where lanes on either side of the vehicle will be highlighted with tick red lines to mark the path for the car to take. One we get this to work with the test images, the pipeline is extended to process a full test video. 

*   Road condition: The input is video and assumption is it is taken from a camera mounted on the dashboard. The car is driven on a straight road (without curves) that the images on a straight road. 
It is daytime with sunny weather.


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---



##**Pipeline** 

###**Reading the image**
* Read the image through matplotlib's imread function. This function 'return a 3d numpy array (for RGB) 

###**Grayscale**

The image is then converted to grayscale using openCV. This step helps simplify the image for further processing in the coming steps.

###**Gaussian**

*   Next we apply gaussian blur on the image. It helps us reduce noise, keeping us from detecting any less important details on the image such as other cars or lanes outside the current lane of the vehicle

###**Canny Edge**

*   Next step uses Canny edge detection on the image. The Canny edge step detects edges on a image by looking for quick changes in color between a pixel and its neighbors, in our case between the white or yellow lane line and black pixels.

###**Region of interest**

*   Now we define our region of interest. Given the position of the camera the lanes are likely to be in the lower half of the image. It is almost consistently a trapezoid converging on the top after starting wide at the bottom of the image. Picking region can be tricky and can lead to variable results.

###**Hough transform**

*   Once the ROI is defined we run Hough transform to detect lines on our image. This algorithm help select lines passing through each of our edge points. This groups the points that are roughly located on a same line. 

###**Tweak Draw Lines**

*   This of course was the hardest part. Slope of a line = (Y2 - Y1) / (X2 - X1). We use this equation to organize lines by their slope. It is important to point out that the y-axis is inverted in OpenCV when reading images, so positive slopes will be the right lane and negative slopes will be the left lane. 


![alt text][image1]

### Reflection


###2. Identify potential shortcomings with your current pipeline


*   Yellow lines should be masked as white. They don't perform as well as the white lane.'
*   My slope logic does not work with curves and needs to be more fine tuned to handle that. I don't know how to adjust it yet to handle the curves.
*   ROI and thresholds/kernel used for the various steps needs more fine tuning but I don't think they are affecting the curves. 
*   Solution is not too robust right now.




###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
