### EX.NO : 09

### DATE : 

# <p align="center"> Thresholding of Images  </p> 
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:

Load the necessary packages.

### Step2:

Read the Image and convert to grayscale.

### Step3:

Use Global thresholding to segment the image.

### Step4:

Use Adaptive thresholding to segment the image.

### Step5:

Use Otsu's method to segment the image.

### Step6:

Display the results.

## Program

```python
# Load the necessary packages

import cv2
import matplotlib.pyplot as plt
import numpy as np

# Read the Image and convert to grayscale

image=cv2.imread("scenary.jpg")
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

# Use Global thresholding to segment the image

ret, thresh1 = cv2.threshold(image1,100,200,cv2.THRESH_BINARY)
ret, thresh2 = cv2.threshold(image1,100,200,cv2.THRESH_BINARY_INV)
ret, thresh3 = cv2.threshold(image1,100,200,cv2.THRESH_TRUNC)
ret, thresh4 = cv2.threshold(image1,100,200,cv2.THRESH_TOZERO)
ret, thresh5 = cv2.threshold(image1,100,200,cv2.THRESH_TOZERO_INV)


# Use Adaptive thresholding to segment the image

th1=cv2.adaptiveThreshold(image1,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
th2=cv2.adaptiveThreshold(image1,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret2,th3 = cv2.threshold(image1,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","THRESH_BINARY","THRESH_BINARY_INV","THRESH_TRUNC"
       ,"THRESH_TOZERO","THRESH_TOZERO_INV","ADAPTIVE_THRESH_MEAN_C","ADAPTIVE_THRESH_GAUSSIAN_C","OTSU"]
images=[image1,thresh1,thresh2,thresh3,thresh4,thresh5,th1,th2,th3]
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

![image](https://user-images.githubusercontent.com/81132849/169644883-eace79a6-eb68-4ca2-84ac-09b7a8fce71d.png)


### Global Thresholding

![image](https://user-images.githubusercontent.com/81132849/169644925-b498168f-566c-4480-9561-a5b6a6945f1f.png)


### Adaptive Thresholding

![image](https://user-images.githubusercontent.com/81132849/169644949-1cc67aa7-6590-4c9f-9bc6-251478be9d3a.png)

### Optimum Global Thesholding using Otsu's Method

![image](https://user-images.githubusercontent.com/81132849/169644973-4e488768-c6a7-418e-b1c0-495cd716bf8b.png)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

