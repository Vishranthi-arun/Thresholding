# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>
Load the necessary packages.

### Step2:
<br>
Read the Image and convert to grayscale.

### Step3:
<br>
Use Global thresholding to segment the image.



### Step4:
<br>

Use Adaptive thresholding to segment the image.

### Step5:
<br>
Use Otsu's method to segment the image.

### Step 6:
<br>
Display the results.


## Program
```
Developed by: Vishranthi A
Register Number: 212221230124
```
```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image = cv2.imread("super-why.png",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("super-why.png",0)

# Use Global thresholding to segment the image
ret,thresh_img1 = cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(5,5))
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
<br>

![image](https://github.com/Vishranthi-arun/Thresholding/assets/93427278/f546609d-fdcf-4c1c-aa65-07ab4d71d1bf)

<br>
<br>
<br>
<br>

### Global Thresholding
<br>

![image](https://github.com/Vishranthi-arun/Thresholding/assets/93427278/900d2a11-615d-45ae-8f70-4e4c5685980c)

<br>

![image](https://github.com/Vishranthi-arun/Thresholding/assets/93427278/304947a9-feb6-4566-acdd-844a79f01392)

<br>

![image](https://github.com/Vishranthi-arun/Thresholding/assets/93427278/427039eb-0a18-4ae1-8e2b-58d7f414494c)

<br>
<br>

### Adaptive Thresholding
<br>
<br>

![image](https://github.com/Vishranthi-arun/Thresholding/assets/93427278/f6a7d872-d173-447b-b532-7ceba5a6d353)

<br>
<br>
<br>

### Optimum Global Thesholding using Otsu's Method
<br>
<br>

![image](https://github.com/Vishranthi-arun/Thresholding/assets/93427278/fc3f66d4-1276-46aa-8456-6c0d4af91c72)

<br>
<br>
<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

