# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: (./test_images_output/solidWhiteRight.jpg)

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline: First, I converted the images to grayscale, then I applied Gaussian smoothing to apply Canny method. After getting an image with just the edges of the original picture, we selected the vertices for the polygon to mask the edges picture.
After defining the parameters, I applied the Hough on the detected edges (pixels). One internal output of this function is all the lines detected in the region of interest. From these lines, in the draw_lines() function, I calculated the average slope and b on the lines of the left side of the image and for the right side as well. With these parameters of the 2 lines that represent the lanes we calculate the values of X for the top and bottom position of the region of interest.

![alt text](./test_images_output/solidWhiteRight.jpg)


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming what happends when it detects lines from shadows or bright parts. As we are drawing just one straight line for lane, it wont be efficient to detect sharo curves.
Another shortcoming will be hills, as the region of interest will change.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use the information of pass frames in order to improve the accuracy of the next frame lane calculation.
