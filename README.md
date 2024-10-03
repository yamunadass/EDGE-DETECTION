# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

## Output:
### SOBEL EDGE DETECTOR
```import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('HappyFish.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Apply Sobel edge detector
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions

# Apply Laplacian edge detector
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

# Apply Canny edge detector
canny_edges = cv2.Canny(gray_image, 50, 150)

# Display results using Matplotlib
plt.figure(figsize=(12, 12))
```
### ORGINAL IMAGE 
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
![Screenshot 2024-10-03 111327](https://github.com/user-attachments/assets/4080f286-0309-4ee3-a7d9-d9929aab4e38)


### SOBEL EDGE DETECTION
```
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
![Screenshot 2024-10-03 111336](https://github.com/user-attachments/assets/06e03147-5566-44db-bfbf-910fd7226f80)


### LAPLACIAN EDGE DETECTOR
```
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```
![Screenshot 2024-10-03 111344](https://github.com/user-attachments/assets/932571fd-67e7-42aa-88ee-0d96e43c4598)


### CANNY EDGE DETECTOR
```
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
![Screenshot 2024-10-03 111354](https://github.com/user-attachments/assets/5987e5e6-40c0-47f1-b45d-9ef0294c3bca)


### Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
