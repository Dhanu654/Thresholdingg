# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:

Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.
### Step3:

Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.


## Program
~~~

#Developed by : DHANUSYA K
#Register No: 212223230043

# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread('bird.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('bird.jpg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

~~~
## Output

### Original Image
![436937647-c9d8ff96-a1dd-4133-b107-10cb6930af74](https://github.com/user-attachments/assets/2f72bb82-c32d-48b0-b0fb-a0ffd933c152)


### Global Thresholding
![436937708-0e183e51-2a0f-43a9-aae6-227deb72bbf5](https://github.com/user-attachments/assets/c1f7d79e-14e7-4c5d-b5bb-973ae381cd6f) ![436937747-7e6edc1c-5046-4693-9618-59aa6346aa49](https://github.com/user-attachments/assets/584ed364-18a7-420c-8a89-2941dece0759)

![436937804-5910d61f-38f2-4fe1-ae96-ac55dcbe5c08](https://github.com/user-attachments/assets/79431248-4c7e-4fea-aa52-082424a0333e) ![436937856-7969ee46-7a35-4096-bfb3-d47fc2ded8dc](https://github.com/user-attachments/assets/d53d8988-f530-41e9-9a75-f1ee919353f5)
![436937930-a547a891-f8d0-4dc0-b8a4-2fd0743dd804](https://github.com/user-attachments/assets/f254162b-ce8f-4876-ae54-e6c9e32ffcc5)




### Adaptive Thresholding
 ![436938166-7e660bdc-89ad-403c-9e30-4bd2b268b0f3](https://github.com/user-attachments/assets/74a0dfd6-191f-4e0f-bda6-22ad832070f4) ![436938169-64905178-b0c0-476e-99df-8ee30cf4d188](https://github.com/user-attachments/assets/b1f424fd-2acb-4747-9ca9-838e978afb34)





### Optimum Global Thesholding using Otsu's Method
![436938007-0809d08b-a00e-414b-8fe5-faa3c8243f34](https://github.com/user-attachments/assets/f627afd8-04ca-4515-a193-d4d996e2ad0b)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
