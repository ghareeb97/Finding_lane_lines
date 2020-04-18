# **Finding Lane Lines on the Road** 


[//]: # (Image References)

[image1]: Finding_lane_lines_pipeline.png "Pipeline"


---

## Process Pipeline


My pipeline consisted of 5 steps. 
1. I converted the images to grayscale.
2. I applied Gaussian Smoothing to reduce the sharpness of the image.
3. Canny edge detection was used to select the stong gradient no matter the color is.
4. To focus only on the lane I had to apply region masking to remove any unwanted pixels and to be able to select the lane lines only.
5. Hough transform is applied to select the lane lines joining the points/pixels and drawing a line overlayed on it. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by caluclating the gradient/slope and the y-intercept to be able to diffrentiate between the left lin and the right line, after that I had to average the position of each line and extrapolate them to the top and the bottom of the lane.

Below is the output of each step in the image pipeline.

![Finding lane lines pipeline][image1]



### 2. Potential shortcomings with  current pipeline


When I tried to apply the pipeline on the challenge video first without the draw line addition it seems that the shades and many other high gradient pixels other than the lane lines, appear in the canny edge detection and after adding the draw line function it no longer compiles giving error.

### 3. Possible improvements to your pipeline
Detecting the lane lines with more curvature and be able to detect the lines even if shades occur.

