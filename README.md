# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
<br>
Import cv2 and capture the video using cv2.VideoCapture(0)


### Step 2:
<br>
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)


### Step 3:
<br>
Resize the image using cv2.resize() to get a four-split screen.


### Step 4:
<br>
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)


### Step 5:
<br>
Display the image until the key to close the window is pressed.


## Program:

### Developed By: u.srinivas
### Register No: 212221230108

## i) Write the frame as JPG file
``` Python

import cv2
import numpy as np
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video_image.jpg',frame)
    cv2.imwrite("out.jpg",frame)
    if cv2.waitKey(1) == ord(' '):
        break
obj.release()
cv2.destroyAllWindows()
```


## ii) Display the video
``` Python

import cv2
import numpy as np
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video_image',frame)
    if cv2.waitKey(1) == ord(' '):
        break
obj.release()
cv2.destroyAllWindows()
```




## iii) Display the video by resizing the window
``` Python

import cv2
import numpy as np
obj = cv2.VideoCapture(0)
while True:
    cap, frame = obj.read()
    h = int(obj.get(4))
    w = int(obj.get(3))
    sm_frame = cv2.resize(frame, (0,0), fx=0.5 , fy=0.5)
    im = np.ones(frame.shape,np.uint8)*200
    im[125:(h//2)+125,135:(w//2)+135] = sm_frame
    cv2.imshow("Pic",im)
    if cv2.waitKey(1) == ord(' '):
        break
obj.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video

``` Python

import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=cv2.rotate(small_frame,cv2.ROTATE_180)
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord(' '):
        break
cap.release()
cv2.destroyAllWindows()
```







## Output

### i) Write the frame as JPG image
<img width="752" alt="1" src="https://user-images.githubusercontent.com/93427183/226806197-723da666-6303-475f-ba73-b19b960428d7.png">


### ii) Display the video
<img width="557" alt="2" src="https://user-images.githubusercontent.com/93427183/226806204-cdfb658e-07b5-4b3d-8e2b-a919e5421357.png">



### iii) Display the video by resizing the window

<img width="539" alt="3" src="https://user-images.githubusercontent.com/93427183/226806209-5d8282f6-cc7d-42fc-ac07-5e72b63b03a9.png">


### iv) Rotate and display the video


<img width="524" alt="4" src="https://user-images.githubusercontent.com/93427183/226806391-975b95a5-e356-4a36-936a-dd1b120aeec2.png">





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
