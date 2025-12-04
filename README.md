# Histogram-of-an-images

## Name : GOWTHAM V
## Reg.No: 212223100009

## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```
# Name : Gowtham V
# Reg.No.: 212223100009

# In[1]:Write your code to find the histogram of gray scale image and color image channels


import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread("grey.jpg", cv2.IMREAD_GRAYSCALE)
color_image = cv2.imread("color.jpg")
color_image_rgb = cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB)
plt.figure(figsize=(10,5))
plt.subplot(1,2,1)
plt.title("Gray Image")
plt.imshow(gray_image, cmap='gray')
plt.subplot(1,2,2)
plt.title("Color Image")
plt.imshow(color_image_rgb)

plt.show()


# In[2]:Display the histogram of gray scale image and any one channel histogram from color image

import numpy as np

# Read images
grayscale_image = cv2.imread("grey.jpg", cv2.IMREAD_GRAYSCALE)
color_image = cv2.imread("color.jpg")

gray_hist = cv2.calcHist([grayscale_image], [0], None, [256], [0, 256])
blue_hist = cv2.calcHist([color_image], [0], None, [256], [0, 256])
# Plot histograms
plt.figure(figsize=(10,4))

plt.subplot(1,2,1)
plt.title("Grayscale Image Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
plt.plot(gray_hist, color='black')

plt.subplot(1,2,2)
plt.title("Blue Channel Histogram (Color Image)")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
plt.plot(blue_hist, color='blue')

plt.tight_layout()
plt.show()




# In[3]:Write the code to perform histogram equalization of the image. 


# Read grayscale image
gi = cv2.imread("grey.jpg", cv2.IMREAD_GRAYSCALE)
# Resize for better visualization
g = cv2.resize(gi, (500, 400))
# Perform histogram equalization
equ = cv2.equalizeHist(gi)
# Display original and equalized images
plt.figure(figsize=(10,4))

plt.subplot(1,2,1)
plt.title("Original Grayscale Image")
plt.imshow(gi, cmap='gray')
plt.axis("off")

plt.subplot(1,2,2)
plt.title("Equalized Image")
plt.imshow(equ, cmap='gray')
plt.axis("off")

plt.show()

# Compare histograms
plt.figure(figsize=(10,4))

plt.subplot(1,2,1)
plt.title("Before Equalization")
plt.plot(cv2.calcHist([gi], [0], None, [256], [0,256]), color='gray')

plt.subplot(1,2,2)
plt.title("After Equalization")
plt.plot(cv2.calcHist([equ], [0], None, [256], [0,256]), color='black')

plt.tight_layout()
plt.show()

```
## Output:

## Input Grayscale Image and Color Image

<img width="645" height="428" alt="image" src="https://github.com/user-attachments/assets/78d4af69-0ceb-433a-825f-fb25b8ac4a1e" />

<img width="649" height="463" alt="image" src="https://github.com/user-attachments/assets/cbc85d6e-b787-4db3-8864-106b7ad908af" />

## Histogram of Grayscale Image and any channel of Color Image

<img width="1239" height="486" alt="image" src="https://github.com/user-attachments/assets/cce4b82f-e31d-4d46-927e-bd10eb2bbf5f" />

## Histogram Equalization of Grayscale Image.

<img width="642" height="232" alt="image" src="https://github.com/user-attachments/assets/095b82d2-8675-426b-8405-c221bcfc6f8b" />

<img width="1233" height="486" alt="image" src="https://github.com/user-attachments/assets/c048fb0f-125c-4f58-a5a0-63122c9b9b83" />









## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
