# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
## Step 1:
Load the necessary packages.

## Step 2:
Read the Image and convert to grayscale.

## Step 3:
Use Global thresholding to segment the image.

## Step 4:
Use Adaptive thresholding to segment the image.

## Step 5:
Use Otsu's method to segment the image.

## Step 6:
Display the results.

## Program
# DEVELOPED BY : R Brindha
# REG NO : 212222230023
# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
# Read the Image and convert to grayscale
```
image=cv2.imread("F1.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("F1.jpg",0)
```
# Use Global thresholding to segment the image
```
ret,thresh_white1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_white2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_white3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_white4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_white5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```
ret,thresh_white6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Use Otsu's method to segment the image 
```
thresh_white7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_white8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_white1,thresh_white2,thresh_white3,thresh_white4,thresh_white5,thresh_white6,thresh_white7,thresh_white8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output
### Original Image
![k1](https://github.com/Brindha77/Thresholding/assets/118889143/91b8ae8b-f82e-4013-b4f3-30fb29304346)

### Global Thresholding
![k2](https://github.com/Brindha77/Thresholding/assets/118889143/76518d1c-9d55-4864-8309-fde3792082d8)
 
![k3](https://github.com/Brindha77/Thresholding/assets/118889143/0e699afe-962f-4a42-8976-7b2b76bdc875)

### Adaptive Thresholding
![k4](https://github.com/Brindha77/Thresholding/assets/118889143/9003c71c-2a40-4d1d-b98f-acca289f41ed)

### Optimum Global Thesholding using Otsu's Method
![k5](https://github.com/Brindha77/Thresholding/assets/118889143/3475e352-2a38-46fb-8a1d-af62d52149d6)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

