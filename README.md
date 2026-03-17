# THRESHOLDING
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
Use Otsu's method to segment the image and display the results.

## Program
```
 Developed by : R Mounish Vamsi Kumar 
 Register number:212224240096 
```

# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```






# Read the image and convert to grayscale
```
image = cv2.imread('Qn8_thresholding.tif')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
```





# Original Image
```
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
```



# Use Global Thresholding to segment the image
```
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
```



# Use Adaptive Thresholding to segment the image
```
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
```




#  Use Otsu's method to segment the image
```
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
```
```
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

<img width="276" height="266" alt="image" src="https://github.com/user-attachments/assets/06c084a8-5992-4492-aa76-bc465a6a0131" />



### Global Thresholding

<img width="349" height="303" alt="image" src="https://github.com/user-attachments/assets/bb12500c-6950-4de7-9a62-0bda5c8b6e7a" />


### Adaptive Thresholding

<img width="315" height="304" alt="image" src="https://github.com/user-attachments/assets/c0be79e3-0616-4ba6-8c5a-8e80240b22da" />

### Optimum Global Thesholding using Otsu's Method

<img width="327" height="306" alt="image" src="https://github.com/user-attachments/assets/c14dae7b-0d20-437b-b3a8-6ccf0be57ee6" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
