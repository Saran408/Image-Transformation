### EXP NO: 05
### DATE:

# <p align='center'> Image-Transformation</p>
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import the necessary libraries and read the original image and save it a image variable.
### Step2:

Translate the image using Translation_matrix=np.float32([[1,0,120],[0,1,120],[0,0,1]]) Translated_image=cv2.warpPerspective(org_img,Translation_matrix,(col,row))
### Step3:
Scale the image using 
Scaling_Matrix=np.float32([[1.2,0,0],[0,1.2,0],[0,0,1]]) Scaled_image=cv2.warpPerspective(org_img,Scaling_Matrix,(col,row))

### Step4:
Shear the image using 

Shearing_matrix=np.float32([[1,0.2,0],[0.2,1,0],[0,0,1]]) Sheared_image=cv2.warpPerspective(org_img,Shearing_matrix,(col2,int(row1.5)))

### Step5:
Reflection of image can be achieved through the code Reflection_matrix_row=np.float32([[1,0,0],[0,-1,row],[0,0,1]]) Reflected_image_row=cv2.warpPerspective(org_img,Reflection_matrix_row,(col,int(row)))
### Step6:
Rotate the image using Rotation_angle=np.radians(10) Rotation_matrix=np.float32([[np.cos(Rotation_angle),-np.sin(Rotation_angle),0], [np.sin(Rotation_angle),np.cos(Rotation_angle),0], [0,0,1]]) Rotated_image=cv2.warpPerspective(org_img,Rotation_matrix,(col,(row)))
### Step7:
Crop the image using cropped_image=org_img[10:350,320:560]
### Step8:
Display all the Transformed images.
## Program:
```python
Developed By: Saran M
Register Number:212220230044



import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("lion.jpg")
img= cv2.cvtColor (img, cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(img)
plt.show()

i)Image Translation
shape=img.shape
rows, cols, dim = shape

M=np.float32([[1,0,80],
          [0,1,75],
          [0,0,1]])
translated_img=cv2.warpPerspective(img,M,(cols,rows))
plt.axis('off')
plt.imshow(translated_img)
plt.show()

ii) Image Scaling

rows, cols, dim = shape
M = np.float32 ([[1.5, 0, 0],
[0, 1.8, 0],
[0, 0, 1]])

scaled_img = cv2.warpPerspective (img, M, (cols*2, rows*2))
plt.axis ('off')

plt.imshow (scaled_img)
plt.show()

iii)Image Shearing


Mx=np.float32([[1,0.5,0],
          [0,1,75],
          [0,0,1]])
My=np.float32([[1,0,0],
              [0.5,1,0],
               [0,0,1]])
shx_img=cv2.warpPerspective(img,Mx,(int(cols),int(rows)))
shy_img=cv2.warpPerspective(img,My,(int(cols),int(rows)))
plt.axis ('off')

plt.imshow (shx_img)
plt.show()
plt.axis ('off')
plt.imshow (shy_img)
plt.show()

iv)Image Reflection

Mx=np.float32([[1,0,0],
          [0,-1,rows],
          [0,0,1]])
My=np.float32([[-1,0,cols],
              [0,1,0],
               [0,0,1]])
refx_img=cv2.warpPerspective(img,Mx,(int(cols),int(rows)))
refy_img=cv2.warpPerspective(img,My,(int(cols),int(rows)))
plt.axis ('off')

plt.imshow (refx_img)
plt.show()
plt.axis ('off')
plt.imshow (refy_img)
plt.show()

v)Image Rotation

angle=np.radians(27)
Rotation_matrix=np.float32([[np.cos(angle),-np.sin(angle),0],
                                [np.sin(angle),np.cos(angle),0],
                                [0,0,1]])
rotimg=cv2.warpPerspective(img,Rotation_matrix,(int(cols),int(rows)))
plt.axis ('off')

plt.imshow (rotimg)
plt.show()

vi)Image Cropping

cropimg=img[60:400,60:400]
plt.axis ('off')

plt.imshow (cropimg)
plt.show()
```
## Output:
### i)Image Translation

![r1](https://user-images.githubusercontent.com/75235427/166685893-b8e467f7-f184-4610-869f-1ee399b2489d.jpg)


### ii) Image Scaling

![r2](https://user-images.githubusercontent.com/75235427/166685899-fb2aab0a-dda1-4cf4-a385-a81ea206597d.jpg)


### iii)Image shearing
![r3](https://user-images.githubusercontent.com/75235427/166685914-f22ee3d2-53d0-4d1c-8ddf-f784c5f08141.jpg)


### iv)Image Reflection
![r4](https://user-images.githubusercontent.com/75235427/166685928-a88f1272-08eb-42e2-ae75-ba88b508a7ce.jpg)



### v)Image Rotation

![r5](https://user-images.githubusercontent.com/75235427/166685938-b075ae53-58d3-4518-9f6b-acecad94d58f.jpg)





### vi)Image Cropping

![r6](https://user-images.githubusercontent.com/75235427/166685946-fd45f392-0521-4514-b9c1-85c86ced0ac5.jpg)


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
