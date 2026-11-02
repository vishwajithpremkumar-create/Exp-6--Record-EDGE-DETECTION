# Exp-6--Record-EDGE-DETECTION


## Aim

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import all the necessary modules for the program.

### Step 2
Load an image using the `cv2.imread()` function.

### Step 3
Convert the image into grayscale using `cv2.cvtColor()`.

### Step 4
Use the Sobel operator from OpenCV to detect the edges of the image in the horizontal and vertical directions.

### Step 5
Use the Laplacian operator to detect edges based on second-order derivatives.

### Step 6
Use the Canny operator to detect edges in the image.

### Step 7
Display the edge-detected images using Matplotlib.

## Program

**Developed By:** VISHWAJITH P

**Register Number:** 212225220122

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('vishwa.jpeg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')  
```

## Output

### Input Image 

<img width="397" height="518" alt="image" src="https://github.com/user-attachments/assets/41ab4d68-b7e8-47d0-bd5c-b8554f0ac182" />


### 1. Sobel Edge Detector

<img width="378" height="508" alt="image" src="https://github.com/user-attachments/assets/43614745-aad9-4220-81da-cc3dddb73e46" />


### 2. Laplacian Edge Detector

<img width="375" height="412" alt="image" src="https://github.com/user-attachments/assets/651fcc4b-9534-4dea-840d-4e9ddd1c347e" />


### 3. Canny Edge Detector
<img width="381" height="515" alt="image" src="https://github.com/user-attachments/assets/0e2defe9-7a19-4b3f-bc10-c3593b48ae3b" />


## Result

Thus, the edges of the image were detected successfully using Sobel, Laplacian, and Canny edge detectors with OpenCV and Python.
