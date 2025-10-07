## Edge-Linking-using-Hough-Transformm
### Aim :
To write a Python program to detect the lines using Hough Transform.

### Software Required :
Anaconda - Python 3.7

### Algorithm :
#### Step1 :
Import all the necessary modules for the program.
#### Step2 :
Load a image using imread() from cv2 module.
#### Step3 :
Convert the image to grayscale.
#### Step4 :
Using Canny operator from cv2,detect the edges of the image.
#### Step5 :
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

### Program :
```
NAME: DEVA DHARSHINI I
REG: 212223240026
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('exp7img.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
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
### Output :
#### Input image and grayscale image :
<img width="515" height="372" alt="image" src="https://github.com/user-attachments/assets/9161ca7f-d246-4485-895f-4c6ff6414583" />

#### Canny Edge detector output :
<img width="515" height="372" alt="image" src="https://github.com/user-attachments/assets/e6fd5019-4874-4c53-b348-912cc8971dda" />

#### Display the result of Hough transform :
<img width="515" height="372" alt="image" src="https://github.com/user-attachments/assets/f2b52891-c95f-47e9-aefa-6d34a2d568d4" />

### Result :
Thus, the Python program to detect the lines using Hough Transform run successfully.
