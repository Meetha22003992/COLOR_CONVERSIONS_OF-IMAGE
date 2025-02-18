
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

##### Program:ARTIFICIAL INTELLIGENCE AND MACHINE LEARNING
### Developed By:MEETHA PRABHU
### Register Number: 212222240065


## Output:

### i) Read and display the image
<br>INPUT:<br>
```
import cv2
image=cv2.imread('dip.jpeg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('MEETHA',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>OUTPUT<br>
![image](https://github.com/Meetha22003992/COLOR_CONVERSIONS_OF-IMAGE/assets/119401038/2c14c66a-4086-4326-b23a-49671862940c)


### ii)Write the image

<br>INPUT<br>
```
import cv2
image=cv2.imread('dip.jpeg',0)
cv2.imwrite('demos.jpeg',image)
```
<br>OUTPUT<br>
![image](https://github.com/Meetha22003992/COLOR_CONVERSIONS_OF-IMAGE/assets/119401038/aecfd319-d903-4cd1-ae8a-20bc0b0c8037)


### iii)Shape of the Image

<br>INPUT<br>
```
import cv2
image=cv2.imread('dip.jpeg',1)
 print(image.shape)
```
<br>OUTPUT<br>
![image](https://github.com/Meetha22003992/COLOR_CONVERSIONS_OF-IMAGE/assets/119401038/0dc517cb-9309-4f9f-bf10-f8148106cba3)


### iv)Access rows and columns

<br>INPUT<br>
```
    import random
    import cv2
    image=cv2.imread('dip.jpeg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
<br>OUTPUT<br>
![image](https://github.com/Meetha22003992/COLOR_CONVERSIONS_OF-IMAGE/assets/119401038/69329281-080b-4c6b-83f4-fcfc11e47eb3)


### v)Cut and paste portion of image

<br>INPUT<br>
```
   import cv2
   image=cv2.imread('dip.jpeg',1)
   image=cv2.resize(image,(400,400))
   tag =image[150:200,110:160]
   image[110:160,150:200] = tag
   cv2.imshow('partimage1',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
<br>OUTPUT<br>
![image](https://github.com/Meetha22003992/COLOR_CONVERSIONS_OF-IMAGE/assets/119401038/d8a49d01-2730-4e0d-b623-30a9b2e01cee)


### vi) BGR and RGB to HSV and GRAY
<br>INPUT<br>
```
import cv2
img = cv2.imread('dip.jpeg',1)
img = cv2.resize(img,(300,200))
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
<br>OUTPUT<br>
![image](https://github.com/Meetha22003992/COLOR_CONVERSIONS_OF-IMAGE/assets/119401038/876b8814-ddf1-4eb6-a31b-fd354c1995da)

### vii) HSV to RGB and BGR
<br>INPUT<br>
```
import cv2
img = cv2.imread('dip.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>OUTPUT<br>
![image](https://github.com/Meetha22003992/COLOR_CONVERSIONS_OF-IMAGE/assets/119401038/437706f4-f778-492d-9f0b-3b536b0c1d7a)

### viii) RGB and BGR to YCrCb
<br>INPUT<br>
```
import cv2
img = cv2.imread('dip.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>OUTPUT<br>
![Screenshot 2024-02-14 113548](https://github.com/Meetha22003992/COLOR_CONVERSIONS_OF-IMAGE/assets/119401038/fa5e8430-dbeb-485e-86fc-f4c9e1b4ae83)

### ix) Split and merge RGB Image

<br>INPUT<br>
```
import cv2
img = cv2.imread('dip.jpeg',1)
img = cv2.resize(img,(300,200))
​
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
​
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
​
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
​
cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>OUTPUT<br>
![image](https://github.com/Meetha22003992/COLOR_CONVERSIONS_OF-IMAGE/assets/119401038/95e6f998-02a4-4013-b5df-530834f78869)


### x) Split and merge HSV Image
<br>INPUT<br>
```
import cv2
img = cv2.imread("dip.jpeg",1)
img = cv2.resize(img,(300,200))
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
<br>OUTPUT<br>
![image](https://github.com/Meetha22003992/COLOR_CONVERSIONS_OF-IMAGE/assets/119401038/4c08a489-13a6-41a6-9f6c-79f132a61818)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







