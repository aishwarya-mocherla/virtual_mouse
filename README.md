# **AI VIRTUAL MOUSE**
The aim of this project is to develop a system that will allow the user to control their computer cursor using their fingertips and different hand gestures.

 *Tools Used:*
- OpenCV - Python
- MediaPipe 
- AutoPy
- Numpy


#### This project is divided into two parts :
- Developing a hand tracking module
- Using the module to develop the virtual mouse 

# Hand Tracking module 
The main objective of creating this module is to set a base algorithm to use for all the necessary hand and gesture-related projects.

**MediaPipe** is a framework developed by google that constist of various models that allows us to work with fundamental AI problems, such as face detection, moving object tracking, object detection, and a lot of other issues that revolve around the various key points or landmarks of an object.

The model we are working with for this project is the hand tracking model. 

It uses two main features at the backend :
- Palm Detection: provides a cropped image of the hand

![6afb6284-c01f-4aa8-8f75-a2354abd0740](https://user-images.githubusercontent.com/80768666/146142160-517f0c2f-eeb3-4b7a-b5fe-36905cb73f7a.jpg)


- Hand Landmarks: detects the various Landmarks / key points of the hand

**_picture of all the hand key points (famous wala photo) 2 _**



To check whether the system detects your hand, we print the landmark every time the system detects one

**_video of printed landmark 3_**

And if the above condition states true, we proceed to mark the various landmarks on the hands and connect them. 
We do this by using the `mp.solutions.drawing_utils` (for the landmarks) and `.HAND_CONNECTIONS` (for the connections) methods.



https://user-images.githubusercontent.com/80768666/146142921-fea665dd-3a76-4103-92c1-207e04cb44eb.mp4




https://user-images.githubusercontent.com/80768666/146142971-c45c28ba-7bbe-4404-8908-45a6b7a9703f.mp4




With this, the first part of the project that is to create a hand tracking module is completed. This module can now be used as a library for various other projects.

*You can find the primitive, minimum requirements version of the model in the same repository as this.*

# Converting the had movements to mouse movements

Since we need to assign each hand gesture to perform a specific operation, we need to determine if a particular finger is straight up or down. To do that, we create a function that compares the position of the **fingertip** landmarks to the **finger joints** landmarks. If The position of the tip is lower than the joint, it means that the finger is down, and if not, it's up. 





https://user-images.githubusercontent.com/80768666/146143016-cc78eec2-cdad-4d59-bdf2-ea2211edc1e9.mp4


Now that we have our improvised hand tracking module, we start working on the virtual mouse. In addition to OpenCV and MediaPipe libraries, we also use the **AutoPy** library. It is a cross-platform GUI automation library that includes functions for controlling the keyboard and mouse.

### Pointer
We use AutoPy to control and navigate the cursor if the pointer finger is up and the rest of the other fingers are down by using `autopy.mouse.move`
![ca7fd8ae-6c71-4803-94ae-10883df4eeb6](https://user-images.githubusercontent.com/80768666/146143098-541ece3e-2bad-4608-81d4-8bbc96239fd3.jpg)


### Click function
We use AutoPy to left-click if the pointer finger is up and the thumb is out by using `autopy.mouse.click`



https://user-images.githubusercontent.com/80768666/146143255-12d263ee-1a4c-436a-bc5a-d1cbbca6c979.mp4


*Similarly, we can assign many such functionalities to the model*

# Results
 **_final video_**

<p align="right" style="font-style:oblique">This model runs at 30 FPS</p>

## Refrences 

- https://google.github.io/mediapipe/
- https://pypi.org/project/autopy/
- https://docs.opencv.org/4.x/d6/d00/tutorial_py_root.html
- https://www.hindawi.com/journals/jhe/2021/8133076/
- https://www.researchgate.net/publication/347983092_Virtual_Mouse_Control_Using_Hand_Class_Gesture



link the main documentation of OpenCV, mediapipe and autopipe and caption all pictures
