#**Finding Lane Lines on the Road** 

##Writeup Template

###You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then 
1. converted the images to grayhscale;
2. Apply Gaussian filter to smooth the images;
3. Apply Canny algorithm to find the edges of the lane lines in images;
4. Set the region of interest in the images;
5. Apply hough transform to detect the line in the interest region of images;
6. Overlay lanes lines with the origin images and output the result;

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by identifying the end point and the slope. I set slope threshold to distinguishing left lane line and right lane line. I used a simple way to caluate the average value of left lines slope, also the start and end points of lines.Then fit a line through this average point with the average slope. 

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there are too wrong lines recongized as lane lines. Because my method relies on the averge value of slopes and end points of the lines, so it's not so robust.


###3. Suggest possible improvements to your pipeline

A possible improvement would be to distinguish the lines with slopes and positions, filter the wrong lines.
