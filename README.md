
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
### Developed By:ROSELIN MARY JOVITA S
### Register No:212222230122

## i) Write the frame as JPG file
```
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=videoCaptureObject.read()
    cv2.imwrite("webcam.jpg",frame)
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow(' captured image',frame)
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
    cv2.imshow('ROSELIN_212222230122',image)
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
    cv2.imshow('212222230122',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image
![Screenshot 2024-09-28 102125](https://github.com/user-attachments/assets/eb54902c-6443-49f5-815c-90cb80d18f4b)

### ii) Display the video
![Screenshot 2024-09-28 102646](https://github.com/user-attachments/assets/761f6bcb-43d1-4a8f-a6b1-f3d30f4d09a1)


### iii) Display the video by resizing the window
![Screenshot 2024-09-28 102428](https://github.com/user-attachments/assets/ef005f36-c199-4095-98ea-52a1f8e826ab)


### iv) Rotate and display the video

![Screenshot 2024-09-28 102439](https://github.com/user-attachments/assets/5d3dd4c0-1d1c-4dd0-b0c2-97a18f4aa40a)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
