# Exp-5--Record-Implementation-of-Filters-212224230284

## NAME : SWETHA K
## REGISTER NUMBER : 212224230284

## Aim

To implement various smoothing and sharpening filters using OpenCV to reduce noise, smooth image details, enhance edges, and improve the overall quality of an image.

## The program performs the following operations:

Read and display an input image
Apply Averaging filter
Apply Weighted Averaging filter
Apply Gaussian filter
Apply Median filter
Apply Laplacian sharpening using kernel
Apply Laplacian operator
Display all outputs for comparison

## Software Used

Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib


## Procedure

1. Import the required libraries such as OpenCV, NumPy, and Matplotlib.
2. Read the input image using the cv2.imread() function.
3. Convert the image from BGR to RGB format for proper display.
4. Apply the Averaging Filter to smooth the image and reduce noise.
5. Apply the Weighted Averaging Filter using a predefined kernel.
6. Apply the Gaussian Filter to reduce noise while preserving important image details.
7. Apply the Median Filter to remove salt-and-pepper noise from the image.
8. Apply the Laplacian Sharpening Kernel to enhance edges and fine details.
9. Convert the image into grayscale and apply the Laplacian Operator to detect edges.
10. Display the original image and all the filtered images using Matplotlib for comparison

## Program 

## Developed By

## Name: SWETHA K
## Register No: 212224230284

## 1. Smoothing Filters

i) Using Averaging Filter

```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread(r'C:\Users\admin\Downloads\my photo dipt.jpeg')
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```

ii) Using Weighted Averaging Filter

```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```

iii) Using Gaussian Filter

```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

```

iv)Using Median Filter

```
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()

```

## 2. Sharpening Filters

i) Using Laplacian Linear Kernal

```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

```
ii) Using Laplacian Operator

```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()

```

## Output

## Smoothing 

Averaging filter produces blurred image
Weighted averaging provides smoother result with less distortion
Gaussian filter preserves edges better while reducing noise
Median filter removes salt-and-pepper noise effectively








