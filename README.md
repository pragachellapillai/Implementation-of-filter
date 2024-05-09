# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.

### Step 2:
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.

### Step 3:

Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.
### Step 4:
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.

### Step 5 :
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.
### Step 6 :
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.

## Program:
```
 Developed By   :PRAGAHARSHITHA NC
 Register Number: 212222110033
```

### 1. Smoothing Filters

#### i) Using Averaging Filter
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('bunny.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11,11), np. float32)/121
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Orignal')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')
```
#### ii) Using Weighted Averaging Filter
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('bunny.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image4 = cv2.filter2D(image2, -1, kernel2)
plt.imshow(image4)
plt.title('Weighted Averaging Filtered')
```
#### iii) Using Gaussian Filter
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('bunny.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

gaussian_blur = cv2.GaussianBlur(src=image2, ksize=(11,11), sigmaX=0, sigmaY=0)
plt.imshow(gaussian_blur)
plt.title(' Gaussian Blurring Filtered')
```

#### iv) Using Median Filter
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('bunny.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

median=cv2.medianBlur (src=image2, ksize=11)
plt.imshow(median)
plt.title(' Median Blurring Filtered')
```

### 2. Sharpening Filters
#### i) Using Laplacian Kernal
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('bunny.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel3 = np.array([[0,1,0], [1, -4,1],[0,1,0]])
image5 =cv2.filter2D(image2, -1, kernel3)
plt.imshow(image5)
plt.title('Laplacian Kernel')
```
#### ii) Using Laplacian Operator
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread('bunny.jpeg')
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

new_image = cv2.Laplacian (image2, cv2.CV_64F)
plt.imshow(new_image)
plt.title('Laplacian Operator')
```

## OUTPUT:
### 1. Smoothing Filters

#### i) Using Averaging Filter
![image](https://github.com/JoyceBeulah/Implementation-of-filter/assets/118343698/7f88b1c9-a332-4676-9566-297a799b25e3)

#### ii) Using Weighted Averaging Filter
![image](https://github.com/JoyceBeulah/Implementation-of-filter/assets/118343698/d4d8b897-41e9-4fcf-b3aa-f702fd69ae14)


#### iii) Using Gaussian Filter
![image](https://github.com/JoyceBeulah/Implementation-of-filter/assets/118343698/4c9353d0-5f8c-4ea3-9115-b3723d3b0ece)

#### iv) Using Median Filter
![image](https://github.com/JoyceBeulah/Implementation-of-filter/assets/118343698/e06d5c10-671e-4013-98a0-14d73447bfa6)


### 2. Sharpening Filters
#### i) Using Laplacian Kernal
![image](https://github.com/JoyceBeulah/Implementation-of-filter/assets/118343698/02b1c98d-d932-4d9b-afbd-07b0c7cf48e4)


#### ii) Using Laplacian Operator
![image](https://github.com/JoyceBeulah/Implementation-of-filter/assets/118343698/ff69f72c-0da2-46eb-be08-bddc7fa1da96)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
