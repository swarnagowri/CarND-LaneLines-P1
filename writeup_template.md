#**Finding Lane Lines on the Road** 


**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


# Reflections

### Steps followed
1. Convert image to gray scale.
2. Filtered image noise by applying Gaussian smoothing.
3. Used the canny function to detect edges in the image.
4. Applied a region of interest mask so that only the road is covered.
5. Used the hough transform to find line segments from canny edges.
6. Modidied the draw_lines function to average/extrapolate the line segments detected to map out the full extent 
   of the lane. The line segments are separated by using their slope((y2-y1)/(x2-x1)). 
   The left lane is supposed to have a positive slope and the right lane should have a negative slope, but since 
   the y-axis is reversed in the image space, right lane has a positive and the left lane has a negative slope. 
   The position of each of the lines has been averaged and extrapolated to the top and bottom of the lane.

### Shortcomings
After applying the draw lines function on the challenge video, I came to know that this has been optimized
only for straight lines, and for specific region of interest. objects outside the road are also being detected.

### Improvements
Curved lines also need to be detected.
We can also search for colors and brightness and drop all incorrect dark colors