# EX-07 EDGE LINKING HOUGH TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image.

### Step2:
Find the edges in the image using canny detector and display.

### Step3:
Detect points that form a line using HoughLinesP.

### Step4:
Draw lines on the image.

### Step5:
Display the result.

## Program:
```
DEVELOPED BY: Raja R
REGISTER NUMBER: 212222100041
```

### Read image and convert it to grayscale image
```py
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("Solo.jpg",0)
img_c=cv2.imread("Solo.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
### Find the edges in the image using canny detector and display
```py
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Detect points that form a line using HoughLinesP
```py
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```py
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
### Display the result
```py
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
![Screenshot 2024-04-10 104311](https://github.com/Raja8334/Edge-Linking-using-Hough-Transformm/assets/120719634/568f4ee8-bf1a-4735-9a66-16b4c3686ed8)



### Canny Edge detector output
![Screenshot 2024-04-10 104326](https://github.com/Raja8334/Edge-Linking-using-Hough-Transformm/assets/120719634/3221244c-40d8-4a02-a6fd-a7614f719a83)


### Display the result of Hough transform
![Screenshot 2024-04-10 104339](https://github.com/Raja8334/Edge-Linking-using-Hough-Transformm/assets/120719634/6958a14f-dce9-4ad9-903e-29dcb2f9ea4a)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
