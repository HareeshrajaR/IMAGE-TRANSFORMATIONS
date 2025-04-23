# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
Translate the image using a function warpPerpective()

### Step3:
Scale the image by multiplying the rows and columns with a float value.

### Step4:
Shear the image in both the rows and columns.

### Step5:
Find the reflection of the image.

### Step6 :
Rotate the image using angle function.

## Program:
```# Developed By: HAREESH R
# Register Number: 212223230068

import cv2
import numpy as np

# Load the image (Corrected path - use raw string)
image = cv2.imread(r"C:\Users\admin\Downloads\imgage1.webp")  # Make sure the file exists
(h, w) = image.shape[:2]

# ----------------------- Translation -----------------------
# Move image 100 pixels right and 50 pixels down
tx, ty = 100, 50
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])
translated = cv2.warpAffine(image, translation_matrix, (w, h))

# ----------------------- Scaling -----------------------
# Resize by 1.5x horizontally and 0.75x vertically
scaled = cv2.resize(image, None, fx=1.5, fy=0.75, interpolation=cv2.INTER_LINEAR)

# ----------------------- Shearing -----------------------
# Shear image horizontally
shear_matrix = np.float32([[1, 0.5, 0], [0, 1, 0]])  # x-shear
sheared = cv2.warpAffine(image, shear_matrix, (int(w + 0.5 * h), h))

# ----------------------- Reflection (Flipping) -----------------------
# Flip horizontally (mirror image)
h_flip = cv2.flip(image, 1)
# Flip vertically
v_flip = cv2.flip(image, 0)

# ----------------------- Rotation -----------------------
# Rotate by 45 degrees around the center
angle = 45
scale = 1.0
center = (w // 2, h // 2)
rotation_matrix = cv2.getRotationMatrix2D(center, angle, scale)
rotated = cv2.warpAffine(image, rotation_matrix, (w, h))

# ----------------------- Cropping -----------------------
# Crop a region (top-left 200x200)
cropped = image[0:200, 0:200]

# ----------------------- Display Results -----------------------
cv2.imshow("Original", image)
cv2.imshow("Translated", translated)
cv2.imshow("Scaled", scaled)
cv2.imshow("Sheared", sheared)
cv2.imshow("Horizontally Flipped", h_flip)
cv2.imshow("Vertically Flipped", v_flip)
cv2.imshow("Rotated", rotated)
cv2.imshow("Cropped", cropped)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output:
### Original Image:

![Screenshot 2025-04-23 141036](https://github.com/user-attachments/assets/4efac695-734a-45f6-b005-383c419994c7)

### i)Image Translation

![Screenshot 2025-04-23 140557](https://github.com/user-attachments/assets/fdf4b99b-10da-4f27-8b61-ef32dc2016de)


### ii) Image Scaling

![Screenshot 2025-04-23 140648](https://github.com/user-attachments/assets/88ed34ff-8278-4bbd-b550-7558c2f59389)


### iii)Image shearing

![Screenshot 2025-04-23 140717](https://github.com/user-attachments/assets/80fc36c3-52ef-49c2-87e3-af40733d8dc0)


### iv)Image Reflection
#### i) Horizontally Flipped:

![Screenshot 2025-04-23 140832](https://github.com/user-attachments/assets/10a6384c-8bbd-431a-a479-73e17f1bf7af)

#### ii) Vertically Flipped:
![Screenshot 2025-04-23 140914](https://github.com/user-attachments/assets/dfa48538-b9a7-499d-b431-3314e89e69ac)

### v)Image Rotation

![Screenshot 2025-04-23 140942](https://github.com/user-attachments/assets/7398f1cc-d6c5-4b60-9747-bc54e90c349b)


### vi)Image Cropping

![Screenshot 2025-04-23 141002](https://github.com/user-attachments/assets/96f37dae-1b94-4cda-b4fb-bd3f786434f1)


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
