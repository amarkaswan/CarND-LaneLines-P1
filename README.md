# **Finding Lane Lines on the Road** 

## Introduction

---

#### <div style="text-align: justify"> This project is a part of Udacity's Self-Driving Engineer nanodegree program. It aims to create a software pipeline for identifying lane lines on the road in a video recorded by a camera mounted on the car's roof using image processing and computer vision techniques. </div>

---

## Reflection
### 1. Problem Statement
<div style="text-align: justify"> Identification of the lane lines on the road is the first step to build a self-driving car. The lane lines can help in navigating the self-driving cars precisely and prevent road accidents. </div>  

### 2. Solution Approach
<div style="text-align: justify"> I have built a software pipeline to detect lane lines in an image (i.e., a frame of the video) using five core concepts of image processing and computer vision. A brief description of these concepts is as follows. </div>  
 <p></p>

* As a first step, I have converted the input color image into a grayscale image. 
* Next, I have applied the Gaussian filter to minimize the noise in the grayscale image. 
* Next, I have applied the Canny edge detection algorithm on the blur grayscale image to retrieve the edges in the image. 
* Then, I have masked out a quadrilateral region of interest from the image since lane lines in the image are found in a specific area. 
* <div style="text-align: justify">As the last step, I have applied the Hough transform to extract line segments from Canny edges. After that, I have used a filter on the extracted line segments to eliminate probable horizontal line segments. Next, I have divided the extracted line segments into left lane line and right lane line based on their slopes. Finally, I have used linear regression to extrapolate the endpoints of the left lane line and the right lane line. </div>

### 3. Testing
I have tested the software pipeline on a set of test images and the results obtained are shown below.  

<table>
  <tr>
    <td>solidWhiteCurve</td>
     <td>solidWhiteRight</td>
     <td>solidYellowCurve</td>
  </tr>
  <tr>
     <td> <img src="https://github.com/amarkaswan/CarND-LaneLines-P1/blob/main/test_images_output/solidWhiteCurve.jpg" width="329" height="189"> </td>
     <td> <img src="https://github.com/amarkaswan/CarND-LaneLines-P1/blob/main/test_images_output/solidWhiteRight.jpg" width="329" height="189"> </td>
     <td> <img src="https://github.com/amarkaswan/CarND-LaneLines-P1/blob/main/test_images_output/solidYellowCurve.jpg" width="329" height="189"> </td>
  </tr>
  <tr>
    <td>solidYellowCurve2</td>
     <td>solidYellowLeft</td>
     <td>whiteCarLaneSwitch</td>
  </tr>
  <tr>
     <td> <img src="https://github.com/amarkaswan/CarND-LaneLines-P1/blob/main/test_images_output/solidYellowCurve2.jpg" width="329" height="189"> </td>
     <td> <img src="https://github.com/amarkaswan/CarND-LaneLines-P1/blob/main/test_images_output/solidYellowLeft.jpg" width="329" height="189"> </td>
     <td> <img src="https://github.com/amarkaswan/CarND-LaneLines-P1/blob/main/test_images_output/whiteCarLaneSwitch.jpg" width="329" height="189"> </td>
  </tr>
 </table>


### 4. Shortcomings 

<div style="text-align: justify">One potential shortcoming is that all the parameters of the software pipeline are hardcoded. Therefore, it may not be robust for images (or frames) having different sizes and videos recorded with different orientations. In addition, it is likely to fail when the region of the lane lines is changed, such as in an image of a curvy road. </div>

### 5. Possible improvements 

<div style="text-align: justify">A possible improvement would be to adjust the parameters of the software pipeline dynamically for adopting different types of image or video stream configurations.</div>
<p></p>

<div style="text-align: justify">Another possible improvement would be the usage of advanced computer vision techniques to find the lane lines in images of both straight roads and curvy roads.</div>