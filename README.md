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

### Developed By: KEERTHI VASAN A
### Register Number: 212222240048


## 1) Read and display the image
```
import cv2
image = cv2.imread('dog.jpg')
image_resized = cv2.resize(image, (500,500))
plt.imshow(image_resized)
plt.show()
```
![image](https://github.com/user-attachments/assets/7f94e2b0-a118-4606-9374-c4152852cbc3)

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
![image](https://github.com/user-attachments/assets/2e8f3213-3828-46fa-b9c2-9238cb8894a7)

### b) Draw a circle at the centre of the image
```
image2=image_resized.copy()
res1=cv2.circle(image2,(250,225),150,(240,0,0),10)
cv2.imshow('Image Window', res1)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/6dabe5f5-8f7d-4f23-b916-1876a131bcd1)

### c)Draw a rectangle around a specific region in interest
```
import cv2
image3 = image_resized.copy()
start = (0, 0)  # Top-left corner
stop = (image3.shape[1], image3.shape[0]) 
color = (100, 255, 100)
thickness = 10
res2 = cv2.rectangle(image3, start, stop, color, thickness)
cv2.imshow('Image Window', res2)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
![image](https://github.com/user-attachments/assets/05817996-9e58-4e30-8804-a083f4eae601)


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

![image](https://github.com/user-attachments/assets/38187662-c7dd-46d3-88d1-5750afc2378e)


## 3)Image color conversion

### a) RGB TO HSV

```
image5=image_resized.copy()
hsv_image = cv2.cvtColor(image5, cv2.COLOR_RGB2HSV)
cv2.imshow('HSV Image', hsv_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/fefdea33-2285-4fda-a45c-0e281a3d183b)

### b) RGB TO GRAY
```
image6=image_resized.copy()
gray_image = cv2.cvtColor(image6, cv2.COLOR_RGB2GRAY)
cv2.imshow('GrayScale Image', gray_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/f25d1792-3a19-466e-b4a0-9cb0d1454525)

### c) RGB TO YCrCb
```
image7=image_resized.copy()
ycrcb_image = cv2.cvtColor(image7, cv2.COLOR_RGB2YCrCb)
cv2.imshow('YCrCb Image', ycrcb_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/f104bb5b-af9f-46ab-98fa-a5056931de1e)

### d)HSV TO RGB

```
rgb_image=cv2.cvtColor(hsv_image, cv2.COLOR_HSV2RGB)
cv2.imshow('RBG Image', rgb_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/bae6af40-4a69-48cd-b4aa-ce55fa8b7803)

## 4) Access and manipulate image pixels

### a)Accessing pixel at cooridinate (100,100)

```
image8=image_resized.copy()
(b,g,r)=image8[100,100]
print(f"Red: {r}\nGreen: {g}\nBlue: {b}")
```
![image](https://github.com/user-attachments/assets/3933c54b-9996-4839-a5d6-a366b7a22bf4)

### b)Modify the color of the pixel at coordinate(200,200) to white

```
image8[200,200]=(255,255,255)
(b,g,r)=image8[200,200]
print(f"Red: {r}\nGreen: {g}\nBlue: {b}")
```
![image](https://github.com/user-attachments/assets/d0e04787-339c-4dbd-8ffc-17d5954e87ca)

## 5) Image Resizing
```
image9=image_resized.copy()
resized_image=cv2.resize(image9,(image9.shape[0]//2,image9.shape[1]//2))
cv2.imshow('Original image',image_resized)
cv2.imshow('Resized image',resized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/4f0c099c-bc05-4a78-95a4-f4d46dca7b71)

![image](https://github.com/user-attachments/assets/d0483cfa-61eb-4bc0-8b9b-158b91cd24a5)

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
![image](https://github.com/user-attachments/assets/6b3afd98-d520-46c1-a132-c6eb1da4f9e1)

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
![image](https://github.com/user-attachments/assets/3ce58d4e-b7fb-4110-a9a8-9b4b03169ecd)

![image](https://github.com/user-attachments/assets/ece23c04-4818-4612-b7c4-de826f016367)

### b) Flip the original image vertically and display it.

```
image12=image_resized.copy()
res=cv2.rotate(image12,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('ORIGINAL IMAGE',image12)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/user-attachments/assets/3ce58d4e-b7fb-4110-a9a8-9b4b03169ecd)

![image](https://github.com/user-attachments/assets/b77173f0-ef7e-4369-aac3-53f6b5e65479)

## 8) Write and Save the Modified Image
```
image13=image_resized.copy()
cv2.imwrite('tree_pic.jpg',image13)
```

![image](https://github.com/user-attachments/assets/f9df6beb-3392-454b-b2e1-6aa85d8f0b7c)




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed successfully using the python program.







