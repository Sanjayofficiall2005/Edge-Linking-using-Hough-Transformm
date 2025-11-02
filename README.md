# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('me.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]
cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```
## Output

### Input image and grayscale image
<img width="302" height="411" alt="image" src="https://github.com/user-attachments/assets/3cc3acfd-0de5-4d36-8bce-a088c97a23c1" />
<img width="302" height="411" alt="image" src="https://github.com/user-attachments/assets/084b8a19-8401-459d-8e3c-7c36a15d5b7b" />


### Canny Edge detector output
<img width="302" height="411" alt="image" src="https://github.com/user-attachments/assets/ab75679a-fd45-47d7-8b88-e0732067835e" />



### Display the result of Hough transform
<img width="302" height="411" alt="image" src="https://github.com/user-attachments/assets/3a4d9412-6e6e-4eb9-a615-4fcb4d580f93" />

## Result:
Thus the code to perform Edge detection using Hough Transform was written and executed successfully.
