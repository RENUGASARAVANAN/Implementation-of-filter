# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import necessary libraries (cv2, NumPy, Matplotlib) for image loading, filtering, and visualization.

### Step 2:
Load the image using cv2.imread() and convert it to RGB format using cv2.cvtColor() for proper display in Matplotlib.

### Step 3:
Apply different filters:

1.Averaging Filter: Define an averaging kernel using np.ones() and apply it to the image using cv2.filter2D().
2.Weighted Averaging Filter: Define a weighted kernel (e.g., 3x3 Gaussian-like) and apply it with cv2.filter2D().
3.Gaussian Filter: Use cv2.GaussianBlur() to apply Gaussian blur.
4.Median Filter: Use cv2.medianBlur() to reduce noise.
5.Laplacian Operator: Use cv2.Laplacian() to apply edge detection.

### Step 4:
Display each filtered image using plt.subplot() and plt.imshow() for side-by-side comparison of the original and processed images.

### Step 5:
Save or show the images using plt.show() after applying each filter to visualize the effects of smoothing and sharpening.

## Program:
### Developed By :RENUGA S
### Register Number:212222230118

### 1. Smoothing Filters

#### i) Using Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('nat.jpg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
### OUTPUT:
![Screenshot 2024-10-03 114921](https://github.com/user-attachments/assets/a45bbc81-8e0b-45f9-9e46-56b64e07492b)


#### ii) Using Weighted Averaging Filter
```Python
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```
### OUTPUT:
![Screenshot 2024-10-03 114928](https://github.com/user-attachments/assets/ed52d0d3-3da9-4b76-85b3-335ef24cf827)


#### iii) Using Gaussian Filter
```Python

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

### OUTPUT:
![Screenshot 2024-10-03 114935](https://github.com/user-attachments/assets/7fc67d84-1ff7-429c-801f-bf3a2732c997)


#### iv)Using Median Filter
```Python
median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```
### OUTPUT:
![Screenshot 2024-10-03 114942](https://github.com/user-attachments/assets/22180278-95a6-410b-af1e-743ef9d84759)


### 2. Sharpening Filters
#### i) Using Laplacian Linear Kernal
```Python
kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
### OUTPUT:
![Screenshot 2024-10-03 114948](https://github.com/user-attachments/assets/9c13b36f-2718-4de1-8d85-445b02738290)


#### ii) Using Laplacian Operator
```Python
new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```
### OUTPUT:
![Screenshot 2024-10-03 114955](https://github.com/user-attachments/assets/c1bd3027-3e3e-4f42-9611-50dc8d7166b0)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
