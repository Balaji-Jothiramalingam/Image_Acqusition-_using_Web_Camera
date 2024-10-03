### Image Acqusition-using Web Camera
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
# Step 1:
Use cv2.VideoCapture(0) to access web camera.

# Step 2:
Use cv2.imread to read the video or image.

# Step 4:
Use cv2.imshow to show the video.

# Step 5:
End the program and close the output video window by pressing 'q'

## Program:
``` Python
### Developed By:BALAJI J
### Register No:212221243001
```
## i) Write the frame as JPG file

```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)

ret,frame=viedoCaptureObject.read()
cv2.imwrite("webcam_img.jpg",frame)

viedoCaptureObject.release()
cv2.destroyAllWindows()
```


## ii) Display the video

```
import numpy as np
import cv2

cap = cv2.VideoCapture(0)
ret, frame = cap.read()

cv2.imshow('captured_frame', frame)

cv2.waitKey(10000)


cap.release()
cv2.destroyAllWindows()

```


## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)

ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame

cv2.imshow('212222240110_Thiyagarajan',image)

cv2.waitKey(5000)  

image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)

cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video


```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)

ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame

cv2.imshow('212222240110',image)

cv2.waitKey(5000) 

image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)

cap.release()
cv2.destroyAllWindows()
````






## Output

### i) Write the frame as JPG image
![306834696-5c319921-b55e-4ec5-a6f2-f2294b0a8e72](https://github.com/user-attachments/assets/e26534e5-502c-4782-9600-149a6ec5ca19)




### ii) Display the video

![306834875-d29f2b17-edf9-4bbe-906e-b6e5a9424d12](https://github.com/user-attachments/assets/3170cdaa-3bb9-4d40-aed4-017a991ac93e)




### iii) Display the video by resizing the window

![306834824-49686dd1-a328-4909-a5f1-ddf0567ecff6](https://github.com/user-attachments/assets/e61989db-8e10-4208-95af-b811097817ae)



### iv) Rotate and display the video

![306834763-2fe12628-6724-41d5-9e06-15bbfa8eacb2](https://github.com/user-attachments/assets/af425b21-3101-48e2-ad2d-6800a6a5bbb0)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
