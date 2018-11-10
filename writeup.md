# **Finding Lane Lines on the Road** 

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

My pipeline consisted of 6 steps. 
1. Converted the images to grayscale
2. Used Gaussian blur to smooth them
3. Applied Canny to detect edges
4. Preserved one interested polygon image region
5. Transformed the images with Hough to find lane lines
6. Drawed the lane lines on the images

Operation          | Result      
-------------------|----------
image              | ![image](/test_images/solidWhiteRight.jpg)
Grayscale          | ![Grayscale](/test_images_output/gray.png)
Gaussian smooth    | ![Gaussian Smooth](/test_images_output/blur_gray.png)
Canny edge         | ![Gaussian Smooth](/test_images_output/edges.png)
Polygon region     | ![Gaussian Smooth](/test_images_output/masked_edges.png)
Hough line         | ![Gaussian Smooth](/test_images_output/lines.png)
Line image         | ![Gaussian Smooth](/test_images_output/lines_img.png)


![alt text]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by find the linear equation of left and right lane, i.e. `y = slope*x + bias`. Slope would be the average slope of every piece of left or right lane, and bias is also the average of them. Then drawed the line on the images.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be the drawed line would be disappear in a little moment when the road is not much even or there is a strong sunshine on the road.

Another shortcoming could be the motion of the drawed line would not that smooth.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to tacle more hash environemnt, and extremem weather condition, such as rain, storm, sunny, ...

Another potential improvement could be let the behavior of the drawed line more smooth.
