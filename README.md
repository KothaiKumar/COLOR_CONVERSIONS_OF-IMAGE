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
    image=cv2.imread('dog.jpg',1)
    image=cv2.resize(image,(300,300))
    cv2.imshow('leann',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/511066c7-2da2-4f9d-97e8-d56bb89f2cb2)
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/f72a9c9b-e099-4871-ab63-c120d498df3d)


### ii)Write the image
```python
    import cv2
    image=cv2.imread('dog.jpg',0)
    cv2.imwrite('demos.jpg',image)
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/2fb55463-56ec-40da-8d6b-af8e87a30242)


### iii)Shape of the Image
```python
    import cv2
    image=cv2.imread('dop.jpg',1)
    print(image.shape)
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/e299be1b-47a2-4fc0-a55b-49d95eee71b7)

### iv)Access rows and columns
```python
import random
    import cv2
    image=cv2.imread('dog.jpg',1)
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
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/0aad0969-3f2d-4280-b03f-89e6a2f3aa25)
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/b86a80f7-8a67-43ae-87f5-bc8e5696305e)

### v)Cut and paste portion of image
  ```python
  import cv2
  image=cv2.imread('dog.jpg',1)
  image=cv2.resize(image,(300,300))
  tag =image[150:200,110:160]
  image[110:160,150:200] = tag
  cv2.imshow('image1',image)
  cv2.waitKey(0)
  cv2.destroyAllWindows()
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/3330886b-5a0b-4d66-b7e4-4e3c59f3b08c)
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/6c20b5b4-bca6-4347-8001-e7f8e0c86184)

### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('dog.jpg',1)
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
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/b7cab5a1-2df4-405a-bb55-87f1b5f8c36d)
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/2067c42a-2f5c-4bbc-8140-7e13c4962c24)

### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('dog.jpg')
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
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/cf2537b6-2e22-4a8a-893f-bcc37a229a24)
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/cc28f84b-de30-4da5-8966-b275e6dc7dd3)

### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('dog.jpg')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/c95783dd-eaad-44c5-a4d2-2ce12a4ef38c)
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/1ee13c7f-63bf-47ba-ba8b-4cfd721418b9)

### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('dog.jpg',1)
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
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/c701f36f-0ec3-49a4-8f7c-d9f57a4320de)
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/bf25b7be-38f3-4c97-9e0c-4d976d16020e)

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("dog.jpg",1)
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
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/bd36115b-df1d-44bb-8af4-067fe67e0cf8)
![image](https://github.com/KothaiKumar/COLOR_CONVERSIONS_OF-IMAGE/assets/121215739/1fed0ae7-d33e-464a-9381-e9f08f5849e4)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







