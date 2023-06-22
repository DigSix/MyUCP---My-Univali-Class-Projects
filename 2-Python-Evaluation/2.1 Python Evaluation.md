# Avaliação - Linguagem Python
Universidade do Vale do Itajaí\
Curso: Ciência da Computação\
Disciplina: Introdução a Ciência da Computação\
Professor: Felipe Viel [@VielF](https://github.com/VielF)\
Aluno: Diogo Viana [@DigSix](https://github.com/DigSix)
## Morphological Operations
  In this work, the teacher gave us some examples of morphological operations from the OpenCV library:\
erosion, dilation, opening, closing, and gradient We needed to understand and explain them before.\
  All morphological operations are based on the image shape, which is generally used on binary images.\
  The operations need two inputs to work: the image and a kernel, also called a structuring element\
(something like the "instructions" to be followed by the operation).\
  After importing the libraries, we first define the images that will be used, and second, we define the\
kernel. I used two kernels because opening and closing operations didn't work with a 5x5 matrix. There\
is probably a smarter way to do this using the "interations" variable, but it’s work!
```python
import cv2
import numpy as np
from google.colab.patches import cv2_imshow #using google colab

image = cv2.imread("path\of\file", color_scale)
kernel = np.ones((matrix_i, matrix_j), data_type)
```
### Erosion
  Erosion is a method of thinning the image, let's suppose that the black background is equal to 0, and the\
white color is represented by 1. The kernel will pass through the image, and the pixel in the original image\
will be eroded to 0 if one or more of the pixels under the kernel are 0.
```python
erosion = cv2.erode(image,kernel,iterations = 5)
```
### Dilation
  Dilation is a method of thickening the image. Similar to erosion, the kernel also passes through the image,\
but instead of erode the pixel to 0 it will be increased to 1. In both cases, we have the "interations"\
variable that defines the number of times the operation is applied.
```python
dilation = cv2.dilate(image,kernel,iterations = 5)
```
### Opening
  Opening is a more advanced morphological transformation; however, using the known erosion and dilation\
operations to be more precise, opening is an operation that requires an erosion operation inside a dilation\
operation. It's helpful when we want to remove noise from the background.
```python
cv2.morphologyEx(image,cv2.operation,kernel)
```
### Closing
  Closing is the reverse operation of opening and requires a dilation operation inside an erosion operation.\
We can use it when we want to fill holes in an object in the image.
```python
cv2.morphologyEx(image,cv2.operation,kernel)
```
### Gradient
  Morphological gradient is an operation that requires a dilation operation minus an erosion operation. It's\
very useful when you want the contour of the image's shape. In Google Colab, you can see an example\
step-by-step of the above operations in the other code cell.
```python
cv2.morphologyEx(image,cv2.operation,kernel)
```
### References
[OpenCV - Morphological Transformations](https://docs.opencv.org/4.x/d9/d61/tutorial_py_morphological_ops.html)\
[OpenCV - Erosion](https://docs.opencv.org/3.4/d4/d86/group__imgproc__filter.html#gaeb1e0c1033e3f6b891a25d0511362aeb)\
[OpenCV - Dilation.](https://docs.opencv.org/3.4/d4/d86/group__imgproc__filter.html#ga4ff0f3318642c4f469d0e11f242f3b6c)\
[OpenCV - Opening.](https://docs.opencv.org/4.x/d4/d86/group__imgproc__filter.html#ga67493776e3ad1a3df63883829375201f)\
[OpenCV - Closing.](https://docs.opencv.org/4.x/d4/d86/group__imgproc__filter.html#ga67493776e3ad1a3df63883829375201f)\
[OpenCV - Gradient.](https://docs.opencv.org/4.x/d4/d86/group__imgproc__filter.html#ga67493776e3ad1a3df63883829375201f)\
[GeeksforGeeks - OpenCV Python Tutorial.](https://www.geeksforgeeks.org/opencv-python-tutorial/)\
All the text was created by me, but my English is far from perfect, so I used [QuillBot AI](https://quillbot.com/grammar-check?utm_medium=paid_search&utm_source=google&utm_campaign=grammar_developing&campaign_type=search&gclid=CjwKCAjwpuajBhBpEiwA_ZtfhWsK28FJHeXlzj7LCOWqnGie96A5LTBEb_mOuvlEjI5x5UGib0EIaBoCsMYQAvD_BwE) just to not make it ugly.
### Curiosities
  The first function that I created in Python was a line jumper. Do you want to know the motive? I was too lazy to write "\n".😁👍\
It's a small code, but I am orgulosed of it.
```python
def line_jumper(lines):
  for l in range(lines):
    print("\n")
```
