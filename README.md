# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.
## Program:
```
Developed By :Preethi S
Register Number:212223230157
```
```
import cv2

# Provide full path to the image or make sure it's in the same directory as your script
image_path = r"C:\Users\admin\OneDrive\Desktop\imagee.jpg"  # Change this path to your actual image

# Read the image
image = cv2.imread(image_path)

# Check if image is loaded successfully
if image is None:
    print("Error: Image not found. Please check the file path.")
else:
    # Convert to grayscale
    gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

    # Apply Gaussian blur
    img_blurred = cv2.GaussianBlur(gray_image, (3, 3), 0)

    # Sobel edge detection
    sobelx = cv2.Sobel(img_blurred, cv2.CV_64F, 1, 0, ksize=5)
    sobely = cv2.Sobel(img_blurred, cv2.CV_64F, 0, 1, ksize=5)
    sobelxy = cv2.Sobel(img_blurred, cv2.CV_64F, 1, 1, ksize=5)

    # Laplacian edge detection
    laplacian = cv2.Laplacian(img_blurred, cv2.CV_64F)

    # Canny edge detection
    canny_edges = cv2.Canny(img_blurred, 120, 150)

    # Display all images
    cv2.imshow('Original - Grayscale', gray_image)
    cv2.imshow('Sobel X', sobelx)
    cv2.imshow('Sobel Y', sobely)
    cv2.imshow('Sobel XY', sobelxy)
    cv2.imshow('Laplacian', laplacian)
    cv2.imshow('Canny Edges', canny_edges)

    # Wait for any key to close the windows
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
## Output:
### SOBEL EDGE DETECTOR




![image](https://github.com/user-attachments/assets/c804279e-171d-4bb8-aa9a-03c29bad9dc5)




### LAPLACIAN EDGE DETECTOR


![image](https://github.com/user-attachments/assets/f274f256-428b-44d4-b090-1b99f8fdf69f)




### CANNY EDGE DETECTOR


![image](https://github.com/user-attachments/assets/e4594e3a-4dc4-4874-a87b-c0f5f8ef4f84)


## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
