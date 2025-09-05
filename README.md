# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors. 

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically. 

5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

## Program:
```
Developed By: S.Harika
Register Number: 212224240155
```

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image=cv2.imread("image.png")
image.shape
#Display the images.
plt.imshow(image[:,:,::-1])
plt.title("Original Image")
plt.show()
```
### Output:

<img width="828" height="387" alt="Screenshot 2025-09-06 010126" src="https://github.com/user-attachments/assets/0a690824-0b96-4380-96a2-085549f006b9" />

## i)Image Translation
```
tx,ty=100,200
M_translation=np.float32([[1,0,tx],[0,1,ty]])
translated_image=cv2.warpAffine(image,M_translation, (673,419))
plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis("on")
plt.show()
```
## Output:

<img width="803" height="466" alt="Screenshot 2025-09-06 010411" src="https://github.com/user-attachments/assets/3990b69e-8e21-4b4c-8bc7-96f8c6be6349" />

### ii) Image Scaling
```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  # Set title
plt.axis('off')
```
### Output:

<img width="695" height="199" alt="Screenshot 2025-09-06 010558" src="https://github.com/user-attachments/assets/d0bc941f-bf67-4c20-a8ea-a854c05b21e4" />


### iii)Image shearing
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  
plt.title("Sheared Image")  
plt.axis('off')
```
### Output:

<img width="697" height="374" alt="Screenshot 2025-09-06 010642" src="https://github.com/user-attachments/assets/13339bee-2630-419b-822b-58438e3edf9a" />

### iv)Image Reflection
```
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  
plt.title("Reflected Image")  
plt.axis('off')
```
## Output:

<img width="734" height="369" alt="Screenshot 2025-09-06 010755" src="https://github.com/user-attachments/assets/ac4d4462-aaf7-46e8-8bb8-4cf97752b6b5" />

### v)Image Rotation
```
(height, width) = image.shape[:2] 
angle = 45 
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Rotated Image")  
plt.axis('off')
```
## Output:

<img width="691" height="385" alt="Screenshot 2025-09-06 010850" src="https://github.com/user-attachments/assets/d964cf6e-1550-4025-b1a0-428556d19383" />

### vi)Image Cropping
```
x, y, w, h = 100, 100, 200, 150 
cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image")  
plt.axis('off')
```
## Output:

<img width="698" height="547" alt="Screenshot 2025-09-06 010943" src="https://github.com/user-attachments/assets/eeb3371a-99a5-4193-aa98-4914ccf1f09c" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
