# Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By

  ### Name: JEYAARIKARAN .P
  ### Register No: 212224240064

---

## Program

## 1. Smoothing Filters
## i) Using Averaging Filter
```.py
import cv2
import matplotlib.pyplot as plt
import numpy as np

# Read the image
image1 = cv2.imread(r"C:\Users\admin\Downloads\WAP_7.jpg")

# Convert BGR to RGB
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

# Create averaging filter kernel
kernel = np.ones((11, 11), np.float32) / 121

# Apply average filtering
image3 = cv2.filter2D(image2, -1, kernel)

# Display images
plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")

plt.show()

```
<img width="747" height="267" alt="image" src="https://github.com/user-attachments/assets/1308808e-96d3-49b0-adf9-13df5d8c34cd" />



## ii) Using Weighted Averaging Filter
```.py
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
<img width="545" height="383" alt="image" src="https://github.com/user-attachments/assets/c605a38e-94ee-47d2-82b4-ff3e8648a6d7" />



## iii) Using Gaussian Filter
```.py
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
<img width="535" height="385" alt="image" src="https://github.com/user-attachments/assets/61096aa4-b321-4a92-b66b-d1d21d40cb55" />



## iv)Using Median Filter
```.py
median = cv2.medianBlur(image2, 13)
plt.imshow(cv2.cvtColor(median, cv2.COLOR_BGR2RGB))
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
<img width="597" height="435" alt="image" src="https://github.com/user-attachments/assets/623ecaa2-cc8f-48e8-adcc-653c2e119fd0" />



## 2. Sharpening Filters
## i) Using Laplacian Linear Kernal
```.py
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
<img width="688" height="432" alt="image" src="https://github.com/user-attachments/assets/6a20b801-620a-4082-aea4-0ccc5191de03" />

## ii) Using Laplacian Operator
```.py
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

<img width="627" height="418" alt="image" src="https://github.com/user-attachments/assets/3903cb92-78a6-4bce-8475-03f1826922a0" />







##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
