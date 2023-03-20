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

Import cv2 library

### Step 2:

Create a filename.

### Step 3:

create a code for required questions.

### Step 4:

Print the program

### Step 5:

To off the web camera restart .



## Program:
``` Python
### Developed By:
### Register No:

## i) Write the frame as JPG file


import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imwrite('new.jpg',frame)
    result=False
cap.release()
cv2.destroyAllWindows()


## ii) Display the video


import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iii) Display the video by resizing the window


import cv2
import numpy as np
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
    cv2.imshow('myimage',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iv) Rotate and display the video

import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('myimage',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()







```
## Output

### i) Write the frame as JPG image


![image](https://user-images.githubusercontent.com/94165327/226425067-7f186398-256c-4072-a628-3153ea5b35ba.png)



### ii) Display the video


![image](https://user-images.githubusercontent.com/94165327/226425121-32a8ce2c-09ec-435b-8cdf-df3477318400.png)




### iv) Rotate and display the video


![image](https://user-images.githubusercontent.com/94165327/226426665-5663e7ce-6e42-4579-9385-b614dff33d05.png)








## Result:
Thus the image is accessed from webcamera and displayed using openCV.
