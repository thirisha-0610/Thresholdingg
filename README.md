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
image = cv2.imread('rose.jpg')  # Replace with your image file path
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

<img width="219" height="230" alt="500252426-27cf9550-60aa-4bca-8cc7-fa32edd90f63" src="https://github.com/user-attachments/assets/0e19fa03-934f-4b27-9a04-8f27f3610e2b" />

### Global Thresholding
<img width="217" height="269" alt="500252450-92313c2a-64c6-409f-85c6-d8e36663f462" src="https://github.com/user-attachments/assets/37e6936e-445a-4cfc-b1dc-3ae69e593a32" />


### Adaptive Thresholding
<img width="263" height="274" alt="500252477-e03cad2b-75ad-4d6e-9d40-f5b3b7abfa3a" src="https://github.com/user-attachments/assets/538daa96-60f4-4827-8a61-5f20ee10f5db" />


### Optimum Global Thesholding using Otsu's Method

<img width="235" height="274" alt="500252504-03309cf2-058f-4127-9ece-da2d35c308b7" src="https://github.com/user-attachments/assets/15a41747-d05b-4c61-9e76-b0fb44b7b005" />

# RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

