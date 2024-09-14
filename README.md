# COLOR_CONVERSIONS_OF-IMAGE

#### Developed By: ARHAM S
#### Register Number: 212222110005
#### Date: 

## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) 	Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii)	Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
o	Draw a line from the top-left to the bottom-right of the image.
o	Draw a circle at the center of the image.
o	Draw a rectangle around a specific region of interest in the image.
o	Add the text "OpenCV Drawing" at the top-left corner of the image.

### Step3:
o	Convert the image from RGB to HSV and display it.
o	Convert the image from RGB to GRAY and display it.
o	Convert the image from RGB to YCrCb and display it.
o	Convert the HSV image back to RGB and display it.

### Step4:
o	Access and print the value of the pixel at coordinates (100, 100).
o	Modify the color of the pixel at (200, 200) to white.

### Step5:
o	Resize the original image to half its size and display it.
### Step6:
o	Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o	Flip the original image horizontally and display it.
o	Flip the original image vertically and display it.

### Step8:
o	Save the final modified image to your local directory.

### i)Read and Display an Image

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image_path = 'dog.jpg' 
image = cv2.imread(image_path)
plt.figure(figsize=(10, 8))
plt.subplot(3, 3, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
![Screenshot 2024-09-14 112901](https://github.com/user-attachments/assets/b251c56e-9209-4f20-8eb8-e8abb6417297)


### ii)Draw Shapes and Add Text

```
height, width, _ = img.shape

# Define start and stop points based on the image size
start = (9, 9)  # Slight offset from the top left corner
stop = (width - 9, height - 9)  # Slight offset from the bottom right corner

# Define the rectangle color and thickness
color = (100, 255, 100)
thickness = 9

# Draw the rectangle
res_img = cv2.rectangle(img, start, stop, color, thickness)

# Display the image with the rectangle
cv2.imshow('Image Window', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Get image dimensions
height, width, _ = img.shape

# Calculate the center of the image
center_coordinates = (width // 2, height // 2)

# Draw the circle at the center with a radius of 30 and thickness of 5
res = cv2.circle(img, center_coordinates, 30, (255, 0, 0), 5)

# Display the image with the circle
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-09-14 105028](https://github.com/user-attachments/assets/853c60ae-9cc5-43d4-ad3c-61a7a7fc8a9e)

![Screenshot 2024-09-14 105522](https://github.com/user-attachments/assets/c68f1702-8daa-41f2-8a22-f4155b603e9a)


### iii)Image Color Conversion
```
# Convert to HSV
image_hsv = cv2.cvtColor(image, cv2.COLOR_BGR2HSV)
# Convert to GRAY
image_gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Convert to YCrCb
image_ycrcb = cv2.cvtColor(image, cv2.COLOR_BGR2YCrCb)
# Convert HSV back to RGB
image_rgb_from_hsv = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2BGR)


plt.subplot(3, 3, 3)
plt.imshow(cv2.cvtColor(image_hsv, cv2.COLOR_BGR2RGB))
plt.title('Image in HSV')
plt.axis('off')

plt.subplot(3, 3, 4)
plt.imshow(image_gray, cmap='gray')
plt.title('Image in GRAY')
plt.axis('off')

plt.subplot(3, 3, 5)
plt.imshow(cv2.cvtColor(image_ycrcb, cv2.COLOR_BGR2RGB))
plt.title('Image in YCrCb')
plt.axis('off')

plt.subplot(3, 3, 6)
plt.imshow(cv2.cvtColor(image_rgb_from_hsv, cv2.COLOR_BGR2RGB))
plt.title('HSV to RGB')
plt.axis('off')
```

![Screenshot 2024-09-14 101831](https://github.com/user-attachments/assets/7caf2bc2-1494-444a-ac6a-b1631e520d4b)

### iv)Access and Manipulate Image Pixels

```
pixel_value = image[100, 100]  # Access pixel value at (100, 100)
print(f'Pixel value at (100, 100): {pixel_value}')
image[200, 200] = [255, 255, 255]  # Set pixel color at (200, 200) to white

# Display updated image with manipulated pixels
plt.subplot(3, 3, 7)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Image with Manipulated Pixels')
plt.axis('off')
```

![Screenshot 2024-09-14 101259](https://github.com/user-attachments/assets/68ad884b-0ade-4e89-8bfb-4f3a9a1c3560)
![Screenshot 2024-09-14 105920](https://github.com/user-attachments/assets/c6662ddf-e7f2-4ac4-98aa-5d8675f537b0)
![Screenshot 2024-09-14 110041](https://github.com/user-attachments/assets/79d02fad-5076-4b1a-9700-a242fc82ecd5)
![Screenshot 2024-09-14 110352](https://github.com/user-attachments/assets/0b2092e7-ccda-4fdd-abd5-f3bf7f0ef586)


### v)Image Resizing
```
import cv2
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('dog.jpeg')  # Make sure to use the correct path to your image

# Resize the image
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))

# Setup for displaying the image using Matplotlib
plt.subplot(3, 3, 8)  # Positioning the image at the 8th subplot in a 3x3 grid
plt.imshow(cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title('Resized Image')
plt.axis('off')  # Turn off the axis

# Display the plot
plt.show()

```
![Screenshot 2024-09-14 111351](https://github.com/user-attachments/assets/b58e6158-f799-4d1d-9410-08439e4499f4)


### vi)Image Cropping
```
import cv2
import matplotlib.pyplot as plt

# Load the image using cv2
image = cv2.imread('dog.jpeg')

# Crop the image (e.g., keeping the center portion)
# Let's say you want to crop the image by slicing from [y1:y2, x1:x2]
crop_img = image[100:400, 150:450]  # Adjust these numbers based on your image size

# Plot the cropped image
plt.subplot(3, 3, 8)  # Position it in the 8th subplot of a 3x3 grid
plt.imshow(cv2.cvtColor(crop_img, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for correct color display
plt.title('Cropped Image')
plt.axis('off')  # Hide the axes

plt.show()  # Display the cropped image


```
![Screenshot 2024-09-14 111637](https://github.com/user-attachments/assets/ee1dd366-906a-4898-a6c2-1b0816479a96)


### vii)Image Flipping
```
import cv2
import matplotlib.pyplot as plt

# Load the image using cv2
image = cv2.imread('dog.jpeg')

# Flip the image
flipped_image_horizontal = cv2.flip(image, 1)  # Horizontal flip
flipped_image_vertical = cv2.flip(image, 0)    # Vertical flip

# Plot the horizontally and vertically flipped images
plt.figure(figsize=(10, 8))

# Horizontally flipped image
plt.subplot(1, 2, 1)  # 1 row, 2 columns, position 1
plt.imshow(cv2.cvtColor(flipped_image_horizontal, cv2.COLOR_BGR2RGB))
plt.title('Flipped Horizontally')
plt.axis('off')

# Vertically flipped image
plt.subplot(1, 2, 2)  # 1 row, 2 columns, position 2
plt.imshow(cv2.cvtColor(flipped_image_vertical, cv2.COLOR_BGR2RGB))
plt.title('Flipped Vertically')
plt.axis('off')

# Show both images
plt.show()

```

![Screenshot 2024-09-14 112408](https://github.com/user-attachments/assets/79c8a4ae-4792-4a88-abd2-c3f0c2915def)



### viii)Write and Save the Modified Image
```
output_path = 'modified_image.jpg'
cv2.imwrite(output_path, image)

plt.show()

```


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed  successfully using the python program.







