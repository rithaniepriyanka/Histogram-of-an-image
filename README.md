# Histogram and Histogram Equalization of an image
## AIM
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read two images, Color image and Gray Scale image.

### Step2:
Calculate the Histogram of Gray scale image and any one channel of the color image.

### Step3:
Display the histograms.

### Step4:
Equalize the grayscale image.

### Step5:
Display the equalized grayscale image.

## Program:
```python
# Developed By: J . RITHANIEPRIYANKA
# Register Number: 212220230039
import cv2
import matplotlib.pyplot as plt
Gray_image=cv2.imread('rithu4.jpeg')
Color_image=cv2.imread('rithu5.jpeg')
plt.imshow(Gray_image)
plt.show()
plt.imshow(Color_image)
plt.show()

# Write your code to find the histogram of gray scale image and color image channels.
hist = cv2.calcHist([Gray_image], [0], None, [256], [0,256])
plt.figure()
plt.title("Histogram")
plt.xlabel('grayscale value')
plt.ylabel('pixel count')
plt.stem(hist)
plt.show()

# Display the histogram of gray scale image and any one channel histogram from color image

hist1=cv2.calcHist([Color_image], [1], None, [256], [0,256])
plt.figure()
plt.title("Histogram")
plt.xlabel('grayscale value')
plt.ylabel('pixel count')
plt.stem(hist)
plt.show()

# Write the code to perform histogram equalization of the image. 

import cv2
Gray_image=cv2.imread('rithu4.jpeg',0)
equalize=cv2.equalizeHist(Gray_image)
#resizing image 
Gray_image= cv2.resize(Gray_image, (270,190))
equalize= cv2.resize(equalize, (270,190))
#output
cv2.imshow('GRAY IMAGE',Gray_image)
cv2.imshow('EQUALIZED IMAGE',equalize)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output:
### Input Grayscale Image and Color Image

![DI-EXP4-A](https://user-images.githubusercontent.com/75235132/165235013-8ed286be-d059-44cf-ae0f-6ecc66f03919.png)

### Histogram of Grayscale Image and any channel of Color Image

![DI-EXP4-B](https://user-images.githubusercontent.com/75235132/165235023-a37ca577-7e23-4505-aa74-a7c8de8bc231.png)

### Histogram Equalization of Grayscale Image

![DI-EXP4-C](https://user-images.githubusercontent.com/75235132/165235057-ebab9098-1df6-49ea-8698-e67006301769.png)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
