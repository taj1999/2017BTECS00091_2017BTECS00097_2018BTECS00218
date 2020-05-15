# Hand-Detection-OpenCV
Detect hand in images and count number of fingers raised using Convex Hull algorithm in OpenCV lib in Python

## Steps Involved
1. Find the ROI (Region of Interest)

2. Hand Segmentation : Convert the video frame from BGR to HSV(or Gray)

3. Perform a Threshold operation for hand segmentation based on skin color

4. Perform Dilation and Gaussian blur operation to remove the noise

5. Find the Biggest Contour (this will be our hand) 

6. Perform a Convex Hull around the hand contour

7. Count the no. of convexity defects 

8. Display the number of fingers

## Segmenting the Hand Skin
The most common image format is the RGB, where any pixel is composed of the union of three colors (red, green, blue). However, 
for color segmenting, the HSV color space is much better, because there the information of color is dissociated from the 
information of illumination. HSV stands for Hue (the color information), S (Saturation, e.g., the percentage of ‘color’ 
present) and V (Value/brightness, e.g., the percentage of ‘white’ color present). For our convenience we have taken the values of 
Lower skin bound as [0,20,70] and Upper skin bound as [20,255,255].

### Note : 
In order to get good segmentation you need to fine-tune HSV bounds

## Convex Hull
In order to detect fingertips, we are going to use the Convex Hull technique. In mathematics, Convex Hull is the 
smallest convex set that contains a set of points. And a convex set is a set of points such that, if we trace a straight 
line from any pair of points in the set, that line must be also be inside the region. The result is the smooth 
region, much easier to be analysed than the original contour, that contains many imperfections.

## Results

![image](https://user-images.githubusercontent.com/63634891/82060456-0ee83e80-96e5-11ea-86c6-fd4de68417f2.png)


![image](https://user-images.githubusercontent.com/63634891/82061345-34297c80-96e6-11ea-9375-19ea5c6f9301.png)


![image](https://user-images.githubusercontent.com/63634891/82061407-4c010080-96e6-11ea-89fa-cfd2062d0984.png)
