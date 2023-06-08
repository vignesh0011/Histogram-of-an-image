## EX.NO: 04<br>
## DATE: 
## <p align="center">HISTOGRAM AND HISTOGRAM EQUALISATION OF AN IMAGE</p>

## Aim:
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

### Step4:
cv2.equalize() is used to transform the gray image to equalized form.

### Step5:
The Histogram of gray scale image and color image is shown.

## Program:
### Developed By: M Vignesh
### Register Number: 212220233002

### a) Write your code to find the histogram of gray scale image and color image channels.
```python
import cv2
import matplotlib.pyplot as plt 

#gray scale and color image  
gray_image = cv2.imread("gray.jpg")
color_image = cv2.imread("tata.jpg")

#resizing and printing the image 
gray_image= cv2.resize(gray_image, (300,170))
cv2.imshow('GRAY IMAGE',gray_image)

color_image= cv2.resize(color_image, (300,170))
cv2.imshow('COLOR IMAGE',color_image)

cv2.waitKey(0)
```

### b) Display the histogram of gray scale image and any one channel histogram from color image
```python
gray_hist=cv2.calcHist([gray],[0],None,[256],[0,255])
color_hist=cv2.calcHist([color],[2],None,[256],[0,255])
plt.figure()
plt.title("GRAY IMAGE")
plt.xlabel("GRAYSCALE VALUE")
plt.ylabel("PIXEL COUNT")
plt.stem(gray_hist)
plt.show()
plt.figure()
plt.title("COLOR IMAGE")
plt.xlabel("COLORSCALE VALUE")
plt.ylabel("PIXEL COUNT")
plt.stem(color_hist)
plt.show()
```

### c) Write the code to perform histogram equalization of the image. 
```python
import cv2
Gray_image=cv2.imread('gray.jpg',0)
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

![image](https://user-images.githubusercontent.com/74660507/165115460-f4bbb7d9-a400-4d02-98ca-3fe7e6a3a4a2.png)



### Histogram of Grayscale Image and any channel of Color Image

![image](https://user-images.githubusercontent.com/74660507/165115673-162c11a5-dd11-4a02-8734-f69a51981a7f.png)




### Histogram Equalization of Grayscale Image

![image](https://user-images.githubusercontent.com/74660507/165115902-d71b87a1-aa7a-4d17-8454-2765086883ad.png)




## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
