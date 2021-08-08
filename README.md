# Real-time Face detection by OpenCV
### **I used the sublime Text to write my code**

## making a simple face detection using openCv here are the steps: 
## 1. installing openCv library 
 ### 1.01: simpley write the following command in the terminal --> pip install openCv-python
## 2. download the face classfier from the following link : https://raw.githubusercontent.com/adarsh1021/facedetection/master/haarcascade_frontalface_default.xml
## 3. import openCv by writing : **import cv2**
## 4. load the classfier or the casecade : **face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')**
## 5.  code (includes grayscale and the modifiers)  : 

```
# To capture video from webcam. 
cap = cv2.VideoCapture(0)
# To use a video file as input (optional) 
# cap = cv2.VideoCapture('filename.mp4')
#loop to keep detecting
while True:
    # Read the frame
    _, img = cap.read()
    #  grayscale conversion
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
    # Detect the faces
    faces = face_cascade.detectMultiScale(gray, 1.1, 4)
    # Draw the rectangle around each face
    for (x, y, w, h) in faces:
        cv2.rectangle(img, (x, y), (x+w, y+h), (255, 0, 0), 2)
    # Display
    cv2.imshow('img', img)
    # exit the loop by pressing the escape key
    k = cv2.waitKey(30) & 0xff
    if k==27:
        break
# Release the VideoCapture object
cap.release()
```
