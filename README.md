## Image_Acqusition-_using_Web_Camera
## Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations. i) Write the frame as JPG ii) Display the video iii) Display the video by resizing the window iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
## Step 1:
Use cv2.VideoCapture(0) to access web camera

## Step 2:
Use cv2.imread to read the video or image

## Step 3:
Use cv2.imwrite to save the image

## Step 4:
Use cv2.imshow to show the video

## Step 5:
End the program and close the output video window by pressing 'q'

## Program:
## Developed By:BALAJI J
## Register No: 212221243001
## i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("exsecond.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('RESULT',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('ksp',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('ksp',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output
## i) Write the frame as JPG image
![image](https://github.com/user-attachments/assets/f8f9c324-4493-454e-a915-94ad0678f0cb)


## ii) Display the video
![image](https://github.com/user-attachments/assets/02dc9f6d-3eaf-45ec-a95e-77f25ac93e3c)


## iii) Display the video by resizing the window

![image](https://github.com/user-attachments/assets/dee26a9a-b744-4caf-8d64-5bcfc5ed629f)

## iv) Rotate and display the video

![image](https://github.com/user-attachments/assets/576aeb0e-4161-4126-aecf-1caacbf4837d)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
