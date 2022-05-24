# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:
```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("dog.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("dog.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_jk1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_jk2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_jk3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_jk4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_jk5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_jk7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_jk8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_jk6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_jk1,thresh_jk2,thresh_jk3,thresh_jk4,thresh_jk5,thresh_jk6,thresh_jk7,thresh_jk8]
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
## OUTPUT:

### Original Image and Grayscale Image
![dip91](https://user-images.githubusercontent.com/75235209/169961072-fcf50eab-01ad-4cad-92a4-a12a1be69214.PNG)



### Global Thresholding
![dip92](https://user-images.githubusercontent.com/75235209/169961297-0f9d51e8-4af2-4592-8561-c1f5393c5f6a.PNG)
![dip93](https://user-images.githubusercontent.com/75235209/169961340-d9702a08-d382-453d-b993-8dcdd7fc7481.PNG)
![image](https://user-images.githubusercontent.com/75235209/169961720-8786bdae-4299-4599-b504-ca9531731f2b.png)
![image](https://user-images.githubusercontent.com/75235209/169961844-eb7171c9-2fd9-4e1d-8fbd-4c4e976cd262.png)
![image](https://user-images.githubusercontent.com/75235209/169962093-8548b617-5109-49a9-9d45-c65c4aab0c60.png)



### Adaptive Thresholding
![image](https://user-images.githubusercontent.com/75235209/169962234-39da2ce9-fd49-458c-88d7-a6b7f7840977.png)
![image](https://user-images.githubusercontent.com/75235209/169962275-724ae6e0-7632-4032-9598-046b72d64dce.png)

### Optimum Global Thesholding using Otsu's Method
![image](https://user-images.githubusercontent.com/75235209/169962162-ce624bba-94b3-4b7c-b8d9-e927e63badd3.png)



## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
