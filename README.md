# **Lane Finding**

## Simple techniques to find lane lines

### Using masking, canny edge detection, and hough transformation
---

**Finding Lane Lines on the Road Project**

The goals / steps of this project are the following:

* Make a pipeline that finds lane lines on the road
  - 1. Defined and mask both white and yellow for the image.
  - 2. Mask edges to create region of interest right in front of vehicle.
  - 3. Applied Canny edge detection with blurred grayscale image.
  - 4. Applied Hough transformation to draw lines.
  - 5. Combined the original image and drawed lines from above steps.

[//]: # (Image References)

[image1]: ./test_images_output/solidWhiteCurve.png
[image2]: ./test_images_output/solidWhiteRight.png
[image3]: ./test_images_output/solidYellowCurve.png
[image4]: ./test_images_output/solidYellowCurve2.png
[image5]: ./test_images_output/solidYellowLeft.png
[image6]: ./test_images_output/whiteCarLaneSwitch.png

[image7]: ./test_images/solidWhiteCurve.png
[image8]: ./test_images/solidWhiteRight.png
[image9]: ./test_images/solidYellowCurve.png
[image10]: ./test_images/solidYellowCurve2.png
[image11]: ./test_images/solidYellowLeft.png
[image12]: ./test_images/whiteCarLaneSwitch.png

---
### README

- The techniques used to detect lane is as seen below and here is a link to my [project code](./Finding_Lane_Lines.ipynb).

![alt text][image2]

### Steps/ Reflection used to achieve lane detection.

#### 1. Description of Pipeline

1. Defined and mask both white and yellow for the image.
2. Mask edges to create region of interest right in front of vehicle.
3. Applied Canny edge detection with blurred grayscale image.
4. Applied Hough transformation to draw lines.
5. Combined the original image and drawed lines from above steps.

* In order to draw a single line on the left and right lanes
  - I modified the draw_lines() function by determine which line is left or right.
  - A slope function is used where the image is looked at 180 degrees
   - left would be greater than 26.52deg 
   - right would be less than 153.48 deg 

* Here are the results **BEFORE** and **AFTER** the pipeline:

* Example 1:
![alt text][image7]
![alt text][image1]

* Example 2:
![alt text][image8]
![alt text][image2]

* Example 3:
![alt text][image9]
![alt text][image3]

* Example 4:
![alt text][image10]
![alt text][image4]

* Example 5:
![alt text][image11]
![alt text][image5]

* Example 6:
![alt text][image12]
![alt text][image6]

* Heres a link to watch the video of the pipeline:

[Video 1:](./test_videos_output/solidWhiteRight.mp4)

[Video 2:](./test_videos_output/solidYellowLeft.mp4)

#### 2. Identify potential shortcomings with your current pipeline

* One potential shortcoming would be it will fail to ititerate in video when the image does not obey the criteria in draw_lines() function. 

* The color selection of white and yellow for roads are consistent, but if whatever reason the road lines are not the 2 mentioned colors, it will not detect.

* The region of interest is also fixed in a pyramid-like shape which if the camera position gets distorted with an accident, the region of interest would not be accurate.


#### 3. Suggest possible improvements to your pipeline

* A possible improvement would be to update the draw_lines function to be more accurate in terms of meeting critia.

* Another potential improvement could be to use HSV instead of RGB in color selection.


