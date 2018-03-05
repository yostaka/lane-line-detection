# **Finding Lane Lines on the Road** 

[//]: # (Image References)

[image1]: ./test_images_output/1_original-image.png "Original"
[image2]: ./test_images_output/2_gray-scale.png "Gray Scale"
[image3]: ./test_images_output/3_blurred-image.png "Blurred"
[image4]: ./test_images_output/4_edge-image.png "Edge"
[image5]: ./test_images_output/5_masked_edge-image.png "Masked edge"
[image6]: ./test_images_output/6_lane-line-on-masked-edge.png "Line on masked edge"
[image7]: ./test_images_output/7_lane-lines-on-original-image.png "Lines on Original"

### Reflection

### 1. Pipeline

My pipeline consisted of following steps.
* Read an image
![alt text][image1]

* Convert an image to grayscale
![alt text][image2]

* Blur the grayscaled image for noise reduction
![alt text][image3]

* Extract edge of the image with Canny Transform
![alt text][image4]

* Masked the edge image to extract interested area
![alt text][image5]

* Calculate left lane line and right lane line
![alt text][image6]

* Draw the lane lines to original image
![alt text][image7]

In order to draw a single line on the left and right lanes, following steps are applied:
* Group lines detected by Canny Transform into left lane lines and right lane lines. 
** The slope value of lines are used to determine if it is for left lane line or right lane line.
** Line with slope values between 0.3 and -0.3 are ignored because these are considered as outliers
* Take (x, y) coordinates of line start and line end, and those cordinates are used as input for linear regression to calculate slope(m) and constant(b) for lane lines


### 2. Potential shortcomings with current pipeline

Followings are potential shortcomings (limitations) with the pipeline:
* when lane lines are not straight lines. In that case, annotated lines would not be aligned with actual lane lines.
* when lane lines length are too short. In that case, annotated lines would not be shown because the pipeline would not identify the lines.
* when horizon line location is changed, the line annotation would not be shown correctly. That might happens when camera angle is changed, or when the car drives on a road with slope.


### 3. Possible improvements to the pipeline

Followings are possible improvements to the pipeline:
* Use of polynominal regression (with higer dimensions) instead of linear regression. It could make the pipeline work for curves (or even more complex) lane shapes.
