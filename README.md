# NAME : ARHAM S
# REG NO : 212222110005

# COLOR_CONVERSIONS_OF-IMAGE
## AIM
Write a Python program using OpenCV that performs the following tasks:

i) Read and Display an Image.

ii) Draw Shapes and Add Text.

iii) Image Color Conversion.

iv) Access and Manipulate Image Pixels.

v) Image Resizing

vi) Image Cropping

vii) Image Flipping

viii) Write and Save the Modified Image


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Load an image from your local directory and display it.
### Step2:
o Draw a line from the top-left to the bottom-right of the image. o Draw a circle at the center of the image. o Draw a rectangle around a specific region of interest in the image. o Add the text "OpenCV Drawing" at the top-left corner of the image.
o Convert the image from RGB to HSV and display it. o Convert the image from RGB to GRAY and display it. o Convert the image from RGB to YCrCb and display it. o Convert the HSV image back to RGB and display it.
### Step4:
o Access and print the value of the pixel at coordinates (100, 100). o Modify the color of the pixel at (200, 200) to white.
### Step5:
o Resize the original image to half its size and display it.
### Step6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o Flip the original image horizontally and display it. o Flip the original image vertically and display it.
### Step8:
o Save the final modified image to your local directory.

## Program and Output:

### Developed By: A.J.PRANAV
### Register Number: 212222230107


## 1) Read and display the image
```
image = cv2.imread('Natural.jpg')
image_resized = cv2.resize(image, (500,500))
plt.imshow(image_resized)
plt.show()
```

![image](https://github.com/user-attachments/assets/d8a50346-4e0b-4e74-9560-e832440e1347)

<br>
<br>

### 2)Draw Shapes and add text

### a)Draw line from top-left to the bottom-right

```
image1=image_resized.copy()
res = cv2.line(image1,(0,0),(500,500),(200,100,205),10)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/3d1b91c2-ac96-4140-9c4c-98b0e325d632)

### b) Draw a circle at the centre of the image
```
image2=image_resized.copy()
res1=cv2.circle(image2,(250,225),150,(240,0,0),10)
cv2.imshow('Image Window', res1)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/2a3c98b1-1b1b-487b-ab78-b0e8c9050625)

### c)Draw a rectangle around a specific region in interest
```
image3=image_resized.copy()
start=(180,150)
stop=(320,400)
color=(100,255,100)
thickness=10
res2=cv2.rectangle(image3,start,stop,color,thickness)
cv2.imshow('Image Window', res2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/2b46b606-84b6-4784-a221-9f2e2824a833)

<br>
<br>

### d)Add the text "OpenCV Drawing" at the top-left corner of the image

```
image4=image_resized.copy()
org=(10,30)
fontface=cv2.FONT_HERSHEY_SIMPLEX
fontScale=1
res3=cv2.putText(image4,"OpenCV Drawing",org,fontface,fontScale,(255,0,0),2)
cv2.imshow('Image Window', res3)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/089e4f53-330f-4328-bd78-659f97ddb950)


## 3)Image color conversion

### a) RGB TO HSV

```
image5=image_resized.copy()
hsv_image = cv2.cvtColor(image5, cv2.COLOR_RGB2HSV)
cv2.imshow('HSV Image', hsv_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/9c6a7ce4-a345-4246-af69-02c4af0d0de8)

### b) RGB TO GRAY
```
image6=image_resized.copy()
gray_image = cv2.cvtColor(image6, cv2.COLOR_RGB2GRAY)
cv2.imshow('GrayScale Image', gray_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/7bb6829d-39b3-4693-b482-010456edfc73)

### c) RGB TO YCrCb
```
image7=image_resized.copy()
ycrcb_image = cv2.cvtColor(image7, cv2.COLOR_RGB2YCrCb)
cv2.imshow('YCrCb Image', ycrcb_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/3179c22a-b458-42c7-a857-36a8aa3ccb9a)

### d)HSV TO RGB

```
rgb_image=cv2.cvtColor(hsv_image, cv2.COLOR_HSV2RGB)
cv2.imshow('RBG Image', rgb_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/521626f7-c1bb-409b-8984-ac3126ed8e3b)

## 4) Access and manipulate image pixels

### a)Accessing pixel at cooridinate (100,100)

```
image8=image_resized.copy()
(b,g,r)=image8[100,100]
print(f"Red: {r}\nGreen: {g}\nBlue: {b}")
```
![image](https://github.com/user-attachments/assets/6561aadf-dbb4-48a5-b0a3-8f3629aad2f6)

### b)Modify the color of the pixel at coordinate(200,200) to white

```
image8[200,200]=(255,255,255)
(b,g,r)=image8[200,200]
print(f"Red: {r}\nGreen: {g}\nBlue: {b}")
```
![image](https://github.com/user-attachments/assets/e7d64314-3f0f-49a9-9db5-24a264fc81f1)

## 5) Image Resizing
```
image9=image_resized.copy()
resized_image=cv2.resize(image9,(image9.shape[0]//2,image9.shape[1]//2))
cv2.imshow('Original image',image_resized)
cv2.imshow('Resized image',resized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/b5745126-62e0-44dc-becc-9c107e15f868)

![image](https://github.com/user-attachments/assets/19593f75-b874-4097-bdc2-e5804009d1fe)

## 6) Image Cropping

```
image10=image_resized.copy()
x, y = 50, 50
width, height = 250, 250
roi = image10[y:y + height, x:x + width]
cv2.imshow('CROPPED IMAGE', roi)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
![image](https://github.com/user-attachments/assets/6391f3e8-b3f6-444d-a66e-5a2abc483083)

## 7) Image Flipping

### a) Flip the original image horizontally and display it.
```
image11=image_resized.copy()
res=cv2.rotate(image11,cv2.ROTATE_180)
cv2.imshow('ORIGINAL IMAGE',image11)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/d6abdb68-55c7-4279-b5cd-22a06dbccdeb)

![image](https://github.com/user-attachments/assets/cf11f20d-5e1d-4a8b-bb76-a7f4865e2b9b)

### b) Flip the original image vertically and display it.

```
image12=image_resized.copy()
res=cv2.rotate(image12,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('ORIGINAL IMAGE',image12)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/f663761f-8ae6-44f4-becd-0fb51f9ce72d)

![image](https://github.com/user-attachments/assets/8fcbecdf-e5e9-4152-b487-f7bd9be8f1df)

## 8) Write and Save the Modified Image
```
image13=image_resized.copy()
cv2.imwrite('Natural.jpg',image13)
```

![image](https://github.com/user-attachments/assets/f9df6beb-3392-454b-b2e1-6aa85d8f0b7c)




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed successfully using the python program.











