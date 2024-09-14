# Working-on-an-image
## AIM:
To write a python program using OpenCV to swap the region of the image.

## Software Required:
Anaconda - Python 3.7
## Algorithm:

1)Load the Images:
<li>Read Image1 and Image2.</li>
<li>Ensure both images are the same size. If not, resize one of the images to match the other.</li>
2)Determine Quadrant Boundaries:

2)Get the height (H) and width (W) of the images.
<li>Divide each image into four equal regions:</li>
<li>Region 1 (R1) = Top-Left (from Image1)</li>
<li>Region 2 (R2) = Top-Right (from Image1)</li>
<li>Region 3 (R3) = Bottom-Left (from Image1)</li>
<li>Region 4 (R4) = Bottom-Right (from Image1)</li>
<li>Region 5 (R5) = Top-Left (from Image2)</li>
<li>Region 6 (R6) = Top-Right (from Image2)</li>
<li>Region 7 (R7) = Bottom-Left (from Image2)</li>
<li>Region 8 (R8) = Bottom-Right (from Image2)</li>
3)Swap Specific Regions:
<li>Swap R1 from Image1 with R8 from Image2.</li>
<li>Swap R2 from Image1 with R7 from Image2.</li>
4)Reconstruct Final Image:
<li>Place the swapped regions into their corresponding positions:</li>
<li>Top-Left: R8 (formerly R1)</li>
<li>Top-Right: R7 (formerly R2)</li>
<li>Bottom-Left: R3 (from Image1)</li>
<li>Bottom-Right: R4 (from Image1)</li>
<li>Similarly, reconstruct the other image using the swapped regions.</li>
5)Resize the Final Images:
<li>Convert the last four digits of the registration number to an even number.</li>
<li>If odd, add 1 to the last digit.</li>
<li>Set this number as the new width (W_final) and height (H_final) for both final images.</li>
<li>Resize both final images to the dimensions (W_final, H_final).</li>
6)Save the Images:
<li>Save the final modified images with appropriate names (e.g., final_image1.jpg and final_image2.jpg).</li>
```

# Program:
```
Developed By: KISHORE.B
Register Number: 212222110020
```

### 1) import file
import cv2
### 2.) Read the image
```
image1= cv2.imread('loki.jpg')
image2= cv2.imread('loki1.jpg')
``` 
### 3.) RESIZE IMAGE:
```
image1_resized = cv2.resize(image1,(400,400))
image2_resized = cv2.resize(image2,(400,400))
```
### 4)image Segmentation.
```
R1 = image1_resized [0:200, 0:200] #Top-Left region
R2 = image1_resized [0:200, 200:400] # Top-right region
R3 =image1_resized [200:400, 0:200] # Bottom-left region
R4 = image1_resized [200:400, 200:400] # Bottom-right 
R5 = image2_resized [0:200, 0:200]
R6= image2_resized [0:200, 200:400] # Top-right region
R7= image2_resized [200:400, 0:200] # Bottom-left region
R8 =image2_resized [200:400, 200:400] 
```
### 5)image read and Displaying image:
```
image1_resized [0:200, 0:200] = R8 
image2_resized [200:400, 200:400] =R3
cv2.imshow('Resized Image 1', image1_resized) 
cv2.imshow('Resized Image 2', image2_resized)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### OUTPUT:
<img height=20% width=50% src=https://github.com/user-attachments/assets/6eaca0cb-7927-44e6-ae3b-f2315b73502f><img height=20% width=50% src=https://github.com/user-attachments/assets/5592ff82-3e3b-4a1e-8b72-04ee7bf8788c>
## Result:
Thus the images are read, displayed, and written ,and swapped the region of the image.
