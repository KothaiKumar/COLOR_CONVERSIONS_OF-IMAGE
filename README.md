# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: Kothai K
### Register Number: 212222240051


## Output:

### i) Read and display the image
```python
    import cv2
    image=cv2.imread('kothai_passport_photo.jpg',1)
    cv2.imshow('Kothai',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/023b18b2-5e26-4adb-bc31-ef5b3141fcf7)

### ii)Write the image
```python
     import cv2
    image=cv2.imread('kothai_passport_photo.jpg',0)
    cv2.imwrite('demo.jpg',image)
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/7eeaa674-7c66-41e4-bf8f-4e7e405f92a9)

### iii)Shape of the Image
```python
        import cv2
    image=cv2.imread('kothai_passport_photo.jpg',1)
    print(image.shape)
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/2130b26e-bd42-4518-b471-7ade4d6bcbe8)

### iv)Access rows and columns
```python
import random
import cv2
image=cv2.imread('kothai_passport_photo.jpg',1)
image=cv2.resize(image,(500,500))
for i in range (250,500):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                     random.randint(0,255),
                     random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/50dad13f-b1e6-44bb-b832-6e6106fdad60)

### v)Cut and paste portion of image
  ```python
  import cv2
image=cv2.imread('kothai_passport_photo.jpg',1)
image=cv2.resize(image,(300,300))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/1b7c174d-2816-4a8e-beee-ad6ae5b3ae43)

### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('kothai_passport_photo.jpg',1)
img = cv2.resize(img,(200,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/1ed7b107-d46f-4e46-92c2-f0fb75f5b6eb)


### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('kothai_passport_photo.jpg')
img = cv2.resize(img,(200,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/8e0621da-8752-4297-9c5c-6fed7331cbc8)


### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('kothai_passport_photo.jpg')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/584cf1f4-9658-4dde-b007-7de3f8254325)


### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('kothai_passport_photo.jpg',1)
img = cv2.resize(img,(200,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/9071f2f0-5052-4844-a8af-46bbd10740a2)

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread('kothai_passport_photo.jpg',1)
img = cv2.resize(img,(200,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```



## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







