# Image Acquisition using Web Camera

### Name : k.pujitha
### Register No : 212223240074

## Aim :
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm :
### Step 1 :

Import the cv2 and numpy package.
<br>
### Step 2 :
Read the Video frame using the cv2.VideoCapture(0)
<br>

### Step 3 :
Write the image using imwrite().
<br>

### Step 4 :
Display the frame using the imshow().
<br>

### Step 5 :
Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().
<br>

## Program :


## i) Write the frame as JPG file 
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
#on the webcamera and read the image
capture=cv2.VideoCapture(0)
ret, frame=capture.read()
#save as frame and stop the webcamera
if ret:
    cv2.imwrite("captured.jpg",frame)
capture.release()
#read the image to display
read_image=cv2.imread("captured.jpg")
```
## ii) Display the video
```
#Display the captured image
plt.imshow(read_image[:,:,::-1])
plt.title("Captured Image")
plt.axis('off')
plt.show()
```
## iii) Display the video by resizing the window
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()


```
## iv) Rotate and display the video
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

## Output :

### i) Write the frame as JPG image

<img width="511" height="411" alt="image" src="https://github.com/user-attachments/assets/da17b172-4a45-4c8e-9f2b-fa029c2659df" />

### ii) Display the video


<img width="520" height="387" alt="image" src="https://github.com/user-attachments/assets/e4782540-4fd1-488b-8227-77556571f11c" />


### iii) Display the video by resizing the window


<img width="261" height="377" alt="image" src="https://github.com/user-attachments/assets/f1b0b217-84a7-42fb-9f38-f47f54dc0a15" />

### iv) Rotate and display the video

<img width="291" height="391" alt="image" src="https://github.com/user-attachments/assets/041c22ee-d6d3-474c-adb3-dddb1dee704c" />

## Result :
Thus the image is accessed from webcamera and displayed using openCV.
