#LGM VIRTUAL INTERNSHIP
#Data Science intern
#Task 4 - Image to Pencil Sketch with Python
# Name - Sweta More

import cv2   

# For Importing a Specific Image From a Folder.

image = cv2.imread('Fly.jpg') 

#Name of image Fly.jpg it will take orginial image. 

grey_img = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY) 

#Color selection command.

invert_img = cv2.bitwise_not(grey_img)

blur_img = cv2.GaussianBlur(invert_img, (21,21), 00)

inverted_img = cv2.bitwise_not(blur_img)

sketch = cv2.divide(grey_img, inverted_img, scale=256.0)

cv2.imwrite('Sketch.jpg', sketch)
#Sketched image as a output