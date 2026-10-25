# Histogram-of-an-images

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:** SARFARAZ I

**Register Number:** 212225230252

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('sv.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('sv.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image

<img width="431" height="558" alt="Screenshot 2026-10-25 093111" src="https://github.com/user-attachments/assets/5c5b4b47-77b1-434d-96d4-ed588eb8fd63" />

### Input Grayscale Image Range
<img width="802" height="556" alt="Screenshot 2026-10-25 093115" src="https://github.com/user-attachments/assets/273f5e6c-3957-4cba-a484-6eb694d3793a" />

### Input Grayscale Image Equalized Histogram
<img width="732" height="578" alt="Screenshot 2026-10-25 093123" src="https://github.com/user-attachments/assets/95976af7-c4c1-4787-ae83-ab2170c69e70" />



### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="417" height="551" alt="Screenshot 2026-10-25 093144" src="https://github.com/user-attachments/assets/063b0886-1c6d-4d49-8432-f1292f49887e" />

### Equalized Image

<img width="381" height="538" alt="Screenshot 2026-10-25 093148" src="https://github.com/user-attachments/assets/674b1cff-6c99-47fd-8a88-a14eb6e57194" />

### Equalized Histogram
<img width="767" height="568" alt="Screenshot 2026-10-25 093152" src="https://github.com/user-attachments/assets/fb53bf8e-70b2-48e4-bb67-0695db2321f6" />

### Final Output of Original Image and Equalized 
<img width="1377" height="523" alt="image" src="https://github.com/user-attachments/assets/6eaa0a49-5317-4f56-89cc-ca8d360357e8" />

### Final Output of Original Image and its Histogram Equalized
<img width="1382" height="442" alt="image" src="https://github.com/user-attachments/assets/063113e9-e85c-42b3-b1ad-0cbeffe57b68" />

## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
