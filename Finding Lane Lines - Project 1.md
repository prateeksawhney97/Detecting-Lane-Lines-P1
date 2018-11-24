# Project 1

# Finding Lane Lines on the Road

### My Pipeline consisted of 6 steps:

1. Conversion of image to grayscale using the grayscale() function.
2. Applying Gaussian blur on the image using the gaussian_blur() function.
3. Converting image to an image with only edges using Canny edge detection. If high contrast in pixel value is found,it is considered as an edge and is detected using the canny() function.
4. To remove unwanted area, the image is masked to remove the unwanted portion using the region_of_interest() helper function.
5. Hough transform is used thereafter via Open CV method which helped connecting lines, we are interested in and in eliminating the rest. In this step we also used the draw_lines() method to add lines over the lanes in the image and extrapolate them.
6. Last step was to merge both the modified image and the original one to produce the result using the weighted_img() function.

### Modification:

The draw_lines() function has to be modified in order to extrapolate the lane lines. For this, 

### Potential shortcomings with my current pipeline:

The only drawback is that when I try to run the "challenge.mp4" video, the lane lines are not recognised correctly. There is a ot of flickering and wrong detection in between when the road is curved left or right. This means the current pipeline is not so good for curved roads.
