# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. My design pipline in functions.

My pipeline consisted of 5 steps. 

Step-1. Converte the images to grayscale via cv2.cvtColor().

Step-2. Use Gaussian blur to make image smooth on related noises via cv2.GaussianBlur() & cv2.Canny().

Step-3. Cut out those region (i.e. triangle of road lane) of interest from original image in step2 via cv2.fillPoly().

Step-4. Call hough algorithm to detect lines in the image from step3 via cv2.HoughLinesP().

Step-5. Combine detected/colored lines into the origin image (via cv2.addWeighted()) to get the final image in which there is a lane line.

BTW, still have been thinking on cv2.line() to improve draw_lines function.

### 2. Identify potential shortcomings with your current pipeline

Only got detecting the line in the center triangle of the road and suffered failed result when sensing curving path.

### 3. Suggest possible improvements to your pipeline

Tune the parameters to meet critical situations in following methods

    gauss_img = gaussian_blur(color_masked, 7)
    
    canny_img = canny(gauss_img, 100, 150) # edge detection
    
    ...
