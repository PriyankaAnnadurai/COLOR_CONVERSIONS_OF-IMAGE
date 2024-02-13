
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
### Step1: Choose an image and save it as a filename.jpg ,
### Step2: Use imread(filename, flags) to read the file.
### Step3: Use imshow(window_name, image) to display the image.
### Step4: Use imwrite(filename, image) to write the image.
### Step5: End the program and close the output image windows.
### Step6: Convert BGR and RGB to HSV and GRAY
### Step7: Convert HSV to RGB and BGR
### Step8: Convert RGB and BGR to YCrCb
### Step9: Split and Merge RGB Image
### Step10: Split and merge HSV Image

##### Program:
```
### Developed By: PRIYANKA.A
### Register Number: 212222230113
```
<table>
  <tr>
    <td width=50%>

### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('city.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('PRIYANKA',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
``` 
  </td>
  <td>

### OUTPUT:
![WhatsApp Image 2024-02-13 at 09 52 21_679351ba](https://github.com/PriyankaAnnadurai/COLOR_CONVERSIONS_OF-IMAGE/assets/118351569/993037ac-626d-4672-8110-39129f14ad0f)

  </td>
  </tr>

   <tr>
    <td width=50%>

### ii)Write the image
```Python
    import cv2
    image=cv2.imread('city.jpg',0)
    cv2.imwrite('demos.jpg',image)
```
  </td>
  <td>

### OUTPUT:
![WhatsApp Image 2024-02-13 at 09 51 56_2c22bacb](https://github.com/PriyankaAnnadurai/COLOR_CONVERSIONS_OF-IMAGE/assets/118351569/06b6f3ee-fbb6-48a6-a5fc-878d4e66251d)

  </td>
  </tr>
  <tr>
    <td width=50%>

### iii)Shape of the Image
```Python
    import cv2
    image=cv2.imread('city.jpg',1)
    print(image.shape)
```
  </td>
  <td>

### OUTPUT:
![WhatsApp Image 2024-02-13 at 09 52 48_67f8b087](https://github.com/PriyankaAnnadurai/COLOR_CONVERSIONS_OF-IMAGE/assets/118351569/2b6872ef-d521-4825-83dc-6dd3e3ed0122)

  </td>
  </tr>
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
    import random
    import cv2
    image=cv2.imread('city.jpg',1)
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
  </td>
  <td width="50%">

### OUTPUT:
![WhatsApp Image 2024-02-13 at 09 53 25_cf0867c9](https://github.com/PriyankaAnnadurai/COLOR_CONVERSIONS_OF-IMAGE/assets/118351569/c09d0d35-37b2-441a-8242-3e21aae049e9)

  </td>
  </tr>
  <tr>
    <td width=50%>
      
### v)Cut and paste portion of image

 ```Python
    import cv2
    image=cv2.imread('city.jpg',1)
    image=cv2.resize(image,(400,400))
    tag =image[150:200,110:160]
    image[110:160,150:200] = tag
    cv2.imshow('partimage1',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td>
    
### OUTPUT:
![WhatsApp Image 2024-02-13 at 09 54 09_b4270c98](https://github.com/PriyankaAnnadurai/COLOR_CONVERSIONS_OF-IMAGE/assets/118351569/8d610f08-0b4b-4ee6-9148-73b7533baac5)

  </td>
  </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('city.jpg',1)
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

### OUTPUT:
![WhatsApp Image 2024-02-13 at 09 55 19_534d446d](https://github.com/PriyankaAnnadurai/COLOR_CONVERSIONS_OF-IMAGE/assets/118351569/2c5aa024-9207-48b6-9b3a-091ce32b7533)


### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('city.jpg')
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

### OUTPUT:
![WhatsApp Image 2024-02-13 at 09 56 02_c0bede67](https://github.com/PriyankaAnnadurai/COLOR_CONVERSIONS_OF-IMAGE/assets/118351569/28389e48-1400-4dd8-8cb6-c59a9e3ecaf7)



### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('city.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:
![WhatsApp Image 2024-02-13 at 09 56 41_ff930f86](https://github.com/PriyankaAnnadurai/COLOR_CONVERSIONS_OF-IMAGE/assets/118351569/0a47ca57-e35e-4822-a504-46918238a9c8)


### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('city.jpg',1)
img = cv2.resize(img,(300,200))

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

### OUTPUT:
![WhatsApp Image 2024-02-13 at 09 57 28_f7b0cd04](https://github.com/PriyankaAnnadurai/COLOR_CONVERSIONS_OF-IMAGE/assets/118351569/8e4187dd-a2cf-4e59-acc8-a03db1a89c2a)



### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("city.jpg",1)
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

### OUTPUT:
![WhatsApp Image 2024-02-13 at 09 58 07_c73520b7](https://github.com/PriyankaAnnadurai/COLOR_CONVERSIONS_OF-IMAGE/assets/118351569/157713cc-a4e7-40b4-b429-374c644a9d64)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.






