# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1: 
 Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:
1. Translation moves the image along the x or y-axis.
2. Scaling resizes the image by scaling factors.
3. Shearing distorts the image along one axis.
4. Reflection flips the image horizontally or vertically.
5. Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:

#### Developed By: Mukil kumar v
#### Register Number: 212222230087
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('asce.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib
```
```
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/fea7bf38-373c-4dbe-870a-507032b93fae)
```
# 1. Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
```
```
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/ebcce5bb-8318-4e8c-85e1-3bd179976cbe)
```
# 2. Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x
```
```
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/d55ddf36-e2ab-4202-b018-2fdc06d73c9e)

```
# 3. Shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
```
```
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/0d0ad710-f258-48bb-8c8d-9731ee0a91f3)

```
# 4. Reflection (Flip)
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
```
```
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/95df3a52-c894-4759-88c6-f09e49dcc9cd)

```
# 5. Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
```
```
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/5adf70cc-f1ba-4429-9b20-2a9656e120bd)

```
# 6. Cropping
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image
```
```
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```

![image](https://github.com/user-attachments/assets/c6f64520-e49b-49f3-9b9a-02245d9251fb)




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
