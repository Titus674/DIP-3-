# Histogram Equalization Using OpenCV (Grayscale & Color Images)
### Name : Titus Ratna Kumar Karivella 
### Register number : 212224230292
## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms 

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.



## Program
```
import cv2
from matplotlib import pyplot as plt
# Load the color image
image = cv2.imread('image.png')
# Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Original Grayscale Image')
plt.axis('off')

hist_original = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
plt.plot(hist_original, color='black')
plt.title('Original Histogram')
plt.xlim([0, 256])

# Apply histogram equalization
equalized_image = cv2.equalizeHist(gray_image)
plt.imshow(equalized_image, cmap='grey')
plt.title('Equalized Image')
plt.axis('off')

hist_original = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])
plt.plot(hist_original, color='black')
plt.title('Equalized Histogram')
plt.xlim([0, 256])
```
### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast
### OUTPUT:

<img width="755" height="595" alt="Screenshot 2026-08-08 090147" src="https://github.com/user-attachments/assets/b951afbd-f34a-4b30-b881-adcf94e37bcb" />

<img width="752" height="642" alt="Screenshot 2026-08-08 090156" src="https://github.com/user-attachments/assets/53d7a2c1-519b-4321-adc8-c0b98f465dac" />

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

<img width="791" height="601" alt="image" src="https://github.com/user-attachments/assets/b9d1270f-0506-4934-a68e-1e9efd7dd372" />

<img width="871" height="623" alt="Screenshot 2026-08-08 090418" src="https://github.com/user-attachments/assets/45afb593-e569-4466-9b57-1fb96a8a9da1" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
