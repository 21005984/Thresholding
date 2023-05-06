# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import required packages.

### Step2:
Read the input image and convert the input colour image into grayscale image.

### Step3:
Apply Global thresholding techniques to segment the image.

### Step4:
Apply Adaptive thresholding techniques to segment the image.


### Step5:
Apply  Otsu's method to segment the image.

### Step 6 :

Display the result of the above methods.
## Program
~~~
DEVELOPED BY : Meiyarasi.V
REGISTER NO :212221230058 

# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image=cv2.imread("uc1.png",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("uc1.png",0)

plt.axis('off')
plt.imshow(image_gray)
plt.show()


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image 

thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)",
"Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu",
       "Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
       images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,
thresh_img6,thresh_img7,thresh_img8]
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

~~~
## Output

### Original Image
  ![output](e1.png)


### Global Thresholding

![output](e2.png)

![output](e3.png)

![output](e4.png)

![output](e5.png)

![output](e6.png)

### Adaptive Thresholding

  ![output](e8.png)

  ![output](e9.png)
### Optimum Global Thesholding using Otsu's Method

  ![output](e7.png)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

