# Exp 3 -Histogram Equalization Using OpenCV (Grayscale & Color Images)


### Developed By: DEEPAK K R

### Register Number: 212225040057
---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---


## Program
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```python
img = cv2.imread('Sus Dog.jpg', cv2.IMREAD_GRAYSCALE)
```
```python
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)
```
```python
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
```python
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
img = cv2.imread('Sus Dog.jpg', cv2.IMREAD_COLOR)
```
```python
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
```python
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
```
```python
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```
```python
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```python
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.ashow()
```
```python
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```python
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed

<img width="768" height="485" alt="Screenshot 2026-08-08 010748" src="https://github.com/user-attachments/assets/b14dde94-2777-4ed9-a04f-8a4ab137f9aa" />

- Histogram of original grayscale image is plotted

<img width="763" height="502" alt="Screenshot 2026-08-08 010757" src="https://github.com/user-attachments/assets/d9a759e9-5c46-4f05-9abe-aef03d95d024" />

- Enhanced image after histogram equalization is displayed

<img width="768" height="485" alt="Screenshot 2026-08-08 010748" src="https://github.com/user-attachments/assets/8c1312c0-6ddd-43da-8052-f12cdec6d337" />


- Histogram of enhanced grayscale image shows improved contrast  

<img width="787" height="505" alt="Screenshot 2026-08-08 010826" src="https://github.com/user-attachments/assets/1713818c-577b-49c5-b93b-826badcd12d2" />


### Color Image Histogram Equalization

- Original color image is displayed

<img width="628" height="553" alt="Screenshot 2026-08-08 010844" src="https://github.com/user-attachments/assets/1396e247-709d-4245-b387-82c9c6a70c63" />

 
- Enhanced image after HSV-based equalization is displayed

<img width="503" height="502" alt="Screenshot 2026-08-08 010850" src="https://github.com/user-attachments/assets/cfe52bd1-e58a-4c8b-81c8-ad3150368399" />



- Histogram of enhanced image shows better intensity distribution

<img width="740" height="502" alt="Screenshot 2026-08-08 010900" src="https://github.com/user-attachments/assets/fbc4feeb-53d6-4047-bb52-bb131e9d0ef0" />

<img width="1481" height="542" alt="Screenshot 2026-08-17 160058" src="https://github.com/user-attachments/assets/40e4ddc2-abd2-4f24-9b18-8a36b277b483" />

<img width="1581" height="492" alt="Screenshot 2026-08-17 160107" src="https://github.com/user-attachments/assets/b286d581-0aa0-4dcf-8775-a460e8832f37" />


---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
