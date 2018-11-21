# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied gaussian blurring followed by canny edge detection. Then I applied a polygonal mask over the lower road region. Finnaly a houg transform was applied to get the straight lines over the lanes. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by first spearating the left and right lines by there slopes. Then I took the mean of right slope, left slope, points in the right lane and points in the left lane. Then I evaluated x-coordinates for lower and upper left lane using y coordinated as the height of image and 350 respectively. Similary, I evaluated x coordinates for right lane using the same y coordinates. 

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the image is zoomed and is taken from the center lane of a 3 lane road. In that case the we will end up selecting the outer lines of the lanes to the left and the right

Another shortcoming could be if there is occulusion i.e. if a car in a different lane driving over the lane or if there is a big truck in front.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to detect multiple left and right lanes.
