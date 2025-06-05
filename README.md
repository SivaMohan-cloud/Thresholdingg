# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import required libraries (OpenCV, NumPy) and load the image in grayscale.

### Step2:
Apply global thresholding using a fixed threshold value.

### Step3:
Apply adaptive thresholding (mean or Gaussian method).

### Step4:
Apply Otsu’s thresholding automatically based on image histogram.

### Step5:
Display and compare the original and thresholded images.

## Program

```python
# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image = cv2.imread('thresh.webp') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.subplot(1, 1, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Original Image")
plt.axis('off')
plt.show()

# Use Global thresholding to segment the image

_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)


# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results

# Global Thresholding
plt.subplot(1, 1, 1)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
plt.show()

# Adaptive Thresholding
plt.subplot(1, 1, 1)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
plt.show()

# Otsu's Method
plt.subplot(1, 1, 1)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
plt.show()



```
## Output

### Original Image
![image](https://github.com/user-attachments/assets/8b632e1c-a998-4fea-8001-425695a588a3)

### Global Thresholding
![image](https://github.com/user-attachments/assets/0796c1a5-e5e8-4b42-b0a0-b99856b70d5a)

### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/dcafcf9c-c5b8-4872-8b6f-c84df19ef2b0)

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/4346bfbd-1230-47c3-8aff-1efba678bd5d)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
