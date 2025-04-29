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

```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the image and convert to grayscale
image_gray = cv2.imread(r"C:\Users\admin\Downloads\digitalimage\catt.jpeg", 0)

# Read the original image for display
image = cv2.imread(r"C:\Users\admin\Downloads\digitalimage\catt.jpeg")
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Global Thresholding
ret, thresh_dipt1 = cv2.threshold(image_gray, 86, 255, cv2.THRESH_BINARY)
ret, thresh_dipt2 = cv2.threshold(image_gray, 86, 255, cv2.THRESH_BINARY_INV)
ret, thresh_dipt3 = cv2.threshold(image_gray, 86, 255, cv2.THRESH_TOZERO)
ret, thresh_dipt4 = cv2.threshold(image_gray, 86, 255, cv2.THRESH_TOZERO_INV)
ret, thresh_dipt5 = cv2.threshold(image_gray, 100, 255, cv2.THRESH_TRUNC)

# Otsu's Thresholding
ret, thresh_dipt6 = cv2.threshold(image_gray, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Adaptive Thresholding
thresh_dipt7 = cv2.adaptiveThreshold(image_gray, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 2)
thresh_dipt8 = cv2.adaptiveThreshold(image_gray, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Titles and Images
titles = [
    "Gray Image",
    "Threshold Image (Binary)",
    "Threshold Image (Binary Inverse)",
    "Threshold Image (To Zero)",
    "Threshold Image (To Zero-Inverse)",
    "Threshold Image (Truncate)",
    "Otsu",
    "Adaptive Threshold (Mean)",
    "Adaptive Threshold (Gaussian)"
]

images = [
    image_gray,
    thresh_dipt1,
    thresh_dipt2,
    thresh_dipt3,
    thresh_dipt4,
    thresh_dipt5,
    thresh_dipt6,
    thresh_dipt7,
    thresh_dipt8
]

# Display Results
for i in range(9):
    plt.figure(figsize=(10, 5))
    plt.subplot(1, 2, 1)
    plt.title("Original Image")
    plt.imshow(image_rgb)
    plt.axis("off")

    plt.subplot(1, 2, 2)
    plt.title(titles[i])
    plt.imshow(images[i], cmap='gray')  # Use cmap='gray' for thresholded images
    plt.axis("off")

    plt.show()

```
## Output

### Original and Gray Image

![image](https://github.com/user-attachments/assets/02cdb090-d6ef-4c0d-a175-71ba357f7617)


### Global Thresholding

![image](https://github.com/user-attachments/assets/d2d9e702-f9ea-4e5d-9092-88a7aca07ccd)


### Adaptive Thresholding
<br>
<br>
<br>
<br>
<br>

### Optimum Global Thesholding using Otsu's Method
<br>
<br>
<br>
<br>
<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
