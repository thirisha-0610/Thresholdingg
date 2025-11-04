# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

Step1 :
Load the image and convert it to grayscale.

Step2 :
Apply a single, fixed threshold value across the entire image.

Step3 :
Calculate and apply a separate, local threshold for different small regions.

Step4 :
Calculate and apply a separate, local threshold for different small regions.

Step5 :
Show the original image and the three segmented (binary) results for comparison.

## Program

```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image = cv2.imread('dog cat.jpg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Use Global thresholding to segment the image
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the results
# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()









```
## Output

### Original Image
<img width="178" height="193" alt="image" src="https://github.com/user-attachments/assets/3196a5d2-1c75-413c-a6af-e6247f84c44a" />

### Global Thresholding
<img width="206" height="218" alt="image" src="https://github.com/user-attachments/assets/b6756e06-38c2-4dd6-a544-b8aababf623d" />

### Adaptive Thresholding
<img width="197" height="219" alt="image" src="https://github.com/user-attachments/assets/dbdb315d-bcc5-4f89-9618-94eae429080a" />


### Optimum Global Thesholding using Otsu's Method
<img width="211" height="222" alt="image" src="https://github.com/user-attachments/assets/eb305203-d155-417c-aa91-e270d5ef0b51" />

# RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

