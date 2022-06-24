### EX NO: 08
### DATE:
# <p align="center">Edge Linking using Hough Transform</p>
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.

### Step2:

Load a image using imread() from cv2 module.

### Step3:

Convert the image to grayscale.

### Step4:

Using Canny operator from cv2,detect the edges of the image.

### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
```
Developed By: KAYALVIZHI M
Register Number: 212220230024
```
```Python

# Read image and convert it to grayscale image

import cv2
import matplotlib.pyplot as plt
import numpy as np
image=cv2.imread("curve.jpg")
cv2.imshow("INPUT IMAGE",image)
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imshow("GRAY_IMAGE",image1)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Find the edges in the image using canny detector and display

canny_edges=cv2.Canny(image1,120,150)
plt.imshow(canny_edges,cmap='gray')
plt.title('Canny Edges')
plt.xticks([])
plt.yticks([])

# Detect points that form a line using HoughLinesP

lines=cv2.HoughLinesP(canny_edges,1,np.pi/180,threshold = 80,minLineLength=50,maxLineGap=250)

# Draw lines on the image

for line in lines:
    x1,y1,x2,y2= line[0]
    cv2.line(image,(x1,y1),(x2,y2),(0,255,0),3)

# Display the result

plt.imshow(image,cmap='gray')
plt.title('image')
plt.xticks([])
plt.yticks([])

```
## Output:

### Input image and grayscale image

![img](https://user-images.githubusercontent.com/75413726/169636227-287eef86-b421-4c4d-9286-efa0c90dcf79.jpg)
![img1](https://user-images.githubusercontent.com/75413726/169636231-d6928c73-d8c6-4aaa-b947-fa96439d8c05.jpg)


### Canny Edge detector output

![img2](https://user-images.githubusercontent.com/75413726/169636237-8e5ec13d-ed99-4726-bd5f-bc429089a67e.jpg)


### Display the result of Hough transform

![img3](https://user-images.githubusercontent.com/75413726/169636241-20c28876-60e4-4d64-950e-54ac61dbc485.jpg)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
