# Histogram-of-an-images
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
```python
# Developed By: Vikaash K S 
# Register Number: 212223240179

import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range=[0,256])
plt.title("original Image")
plt.show()

img_eq=cv2.equalizeHist(img)
plt.hist(img_eq.ravel(),256,range=[0,256])
plt.title('Equalized Histogram')
plt.show()


plt.imshow(img_eq, cmap='gray')
plt.title('Original Image(Equalized)')
plt.show()

img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
img_hsv=cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
img_hsv[:,:,2]=cv2.equalizeHist(img_hsv[:,:,2])
img_eq=cv2.cvtColor(img_hsv,cv2.COLOR_HSV2BGR)


plt.figure(figsize=(12,16))
plt.subplot(121);plt.imshow(img[:,:,::-1]);plt.title('Original Color Image')
plt.subplot(122);plt.imshow(img_eq[:,:,::-1]);plt.title('Equalized Image')

plt.figure(figsize=(12,10))
plt.subplot(221);plt.hist(img.ravel(),256,range=[0,256]);plt.title('Original Image')
plt.subplot(222);plt.hist(img_eq.ravel(),256,range=[0,256]);plt.title('Original Image')
plt.show()

```
## Output:
### Input Grayscale Image and Color Image
![original image gray](https://github.com/user-attachments/assets/a1d244ba-ba00-4fde-9f57-e35e0eec9760)

![original image color](https://github.com/user-attachments/assets/ead3843a-3ce1-460c-9ee3-4502c41069c2)

### Histogram of Grayscale Image and any channel of Color Image
![original image histogram](https://github.com/user-attachments/assets/b95cafe0-ffb7-4a84-895a-67d4930440f2)


### Histogram Equalization of Grayscale Image and Color Image
![Equalized Histogram Gray](https://github.com/user-attachments/assets/e98e7d25-554e-42ce-bd80-0af0c52cd007)

![Equalized Histogram color](https://github.com/user-attachments/assets/90d92d51-e2c3-4abb-b1f1-308f4922d6dc)

### Equalized  Grayscale Image and Color Image 
![original image gray equalized](https://github.com/user-attachments/assets/63065fc6-af69-4573-83ff-12d4659e9cf1)

![original image color equalized](https://github.com/user-attachments/assets/92116745-9873-492f-a209-26ce967765bf)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
