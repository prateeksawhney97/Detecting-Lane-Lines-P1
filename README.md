# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

# Project 1

### Youtube - https://youtu.be/SvEiPJpGhac

### Solid Yellow Left

![](giphy.gif)

### Solid White Right

![](giphy2.gif)


### My Pipeline consisted of 6 steps:

1. Conversion of image to grayscale using the grayscale() function.
2. Applying Gaussian blur on the image using the gaussian_blur() function.
3. Converting image to an image with only edges using Canny edge detection. If high contrast in pixel value is found,it is considered as an edge and is detected using the canny() function.
4. To remove unwanted area, the image is masked to remove the unwanted portion using the region_of_interest() helper function.
5. Hough transform is used thereafter via Open CV method which helped connecting lines, we are interested in and in eliminating the rest. In this step we also used the draw_lines() method to add lines over the lanes in the image and extrapolate them.
6. Last step was to merge both the modified image and the original one to produce the result using the weighted_img() function.

---

### Output Images without extrapolated lane lines:

![download](https://user-images.githubusercontent.com/34116562/48964910-47b7c380-efd8-11e8-9235-4469667cdd3f.png)
![download 1](https://user-images.githubusercontent.com/34116562/48964911-49818700-efd8-11e8-9992-82061b6b9cd7.png)
![download 2](https://user-images.githubusercontent.com/34116562/48964912-4be3e100-efd8-11e8-973c-53c74c083a08.png)
![download 3](https://user-images.githubusercontent.com/34116562/48964913-4be3e100-efd8-11e8-8630-e1d1148d59b5.png)
![download 4](https://user-images.githubusercontent.com/34116562/48964915-4e463b00-efd8-11e8-81e1-17f511c3d629.png)
![download 5](https://user-images.githubusercontent.com/34116562/48964925-ab41f100-efd8-11e8-8ff9-7ae8b62bff22.png)

---

### Modification of draw_line() helper function:

The draw_lines() function has to be modified in order to extrapolate/average/connect the lane lines. For this, created two dictionaries, left_lane_longest{} and right_lane_longest{} to store slope, intercept and length. The slope is calculated for each and every point unless their x -coordinate is equal. On the basis of slope the left and right lanes and segregated. Iteration is done on all the lines that are returned by the hough transform to plot the longest found line.

---

### Potential shortcomings with my current pipeline:

The only drawback is that when I try to run the "challenge.mp4" video, the lane lines are not recognised correctly. There is a lot of flickering and wrong detection in between when the road is curved left or right. This means the current pipeline is not so good for curved roads.

---

### Possible improvements:

Improvements in the Pipeline are needed so that the curved lane lines are also detected without any error. Moreover, the autonomous car will face all kind of road conditions, so some changes must be made to the pipeline in order to make the lane finding error free. The pipeline should be redefined in such a way so that the "challenge.mp4" video is also detected error free.
