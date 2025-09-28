# EXP 02: Image Acquisition using Web Camera

## Aim
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.<br>
i) Write the frame as JPG <br>
ii) Display the video <br>
iii) Display the video by resizing the window<br>
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
### Step 1: 
Start the webcam using cv2.VideoCapture(0) and begin reading frames.
<br>

### Step 2: 
Capture and save a frame as a JPG file using cv2.imwrite().
<br>

### Step 3: 
Display the live video continuously in a window.
<br>

### Step 4:
Resize the frame to half its original size and display the smaller video.
<br>

### Step 5:
Rotate the resized frame (180°) and display it along with the normal frames.
<br>

### Step 6: 
Stop the webcam and close all windows when the user presses ‘q’.
<br>

## Program

### Developed By: POZHILAN V D
### Register No: 212223240118

## i) Write the frame as JPG file
```python
##Developed By: POZHILAN V D
##Reg No: 212223240118
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('photo.jpg',frame)
    cv2.imwrite("pic.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
```



## ii) Display the video
```python
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('video',frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```python
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
    cv2.imshow('resizedvideo',smaller_frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video
```python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('rotatedvideo', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

### Developed By: POZHILAN V D
### Register No: 212223240118


## Output

### i) Write the frame as JPG image
</br>
<img width="773" height="638" alt="Screenshot (16)1" src="https://github.com/user-attachments/assets/3bf38096-295b-468a-b84e-7052c7988352" />


</br>


### ii) Display the video
</br>
<img width="773" height="638" alt="Screenshot (16)1" src="https://github.com/user-attachments/assets/cfca5cd6-e20b-4801-96b0-bcd9e7e49f8e" />

</br>


### iii) Display the video by resizing the window
</br>
<img width="1920" height="1080" alt="Screenshot (13)" src="https://github.com/user-attachments/assets/84390d4c-94c6-465d-9152-8492db3576b7" />

</br>



### iv) Rotate and display the video
</br>
<img width="1058" height="844" alt="image" src="https://github.com/user-attachments/assets/6f40ce48-6daa-475f-97af-67ddc7d87137" />

</br>





## Result
The image was successfully captured from the webcam, saved as a JPG file, and displayed as live video. The video was also shown in resized form and rotated, thus achieving all four image acquisition processes using OpenCV.
