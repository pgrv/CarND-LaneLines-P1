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

My pipeline consisted of multi steps. First, I converted the color space to hls. I learned in the past that this color space is more usefull for lane detection than the rgb. Then I filtered all white and yellow pixels from the image and converted the resulted image to grayscale. I used the canny edge detection and I created a four point region of interest in the bottom of the image. I tried a canny edge detection with adaptive threshold values, but I did not found usefull parameters.
In the ROI I did the hough transformation. Last, I fitted a 1D polynom to the hough lines.

I did not modifie the draw_lines() function himself but I modified the start and end point of both lines. They will drawn from the bottom of the image to 0.6 * image height.


### 2. Suggest possible improvements to your pipeline


I tried moredimensional polynomical fitting on the hough lines but I did not success. I think there is a potential to get better results. So we could get a curve instead of a line.
Maybe with better parameters adaptive canny threshold parameters could lead to better results.
Maybe an outlier filter used on the line slopes could delete some unintended lines.
