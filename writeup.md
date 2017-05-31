# **Finding Lane Lines on the Road** 

## Writeup

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied a canny filter on the image.
Later on I applied a gaussian filter, which smoothes the sharpe edges. The region of interest function cuts of the
enviroment on the image. Final step is to convert the image into hough space to find lines.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by calculating the slope
of the lines. Lines were separated into the ones with negative slope and positive slope (left and right). Afterwards I 
averaged all the slopes to find the line in between. I calculated the point in the bottom of the image and the crossing
point (where left and right line intersects). 


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there are multiple shapes detected as a line, worst thing could
happen if its at the other side of the road. Than it can move the line were hard to the other side of the screen.


### 3. Suggest possible improvements to your pipeline

There is a lot of finetuning possible withe the canny filter. My algorithm is sensitive to sharp edges.

To make the averaging more robost t can be possible to split the images in right and left portion to only allow certain 
 slope vales on each side.
