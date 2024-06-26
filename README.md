# **VIRTUAL MOUSE**
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
<p align="center">
<img width=40% src="virtual_mouse_images/1.jpeg"> &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;
</p>

- Hand Landmarks: detects the various Landmarks / key points of the hand
<p align="center">
<img width=40% src="virtual_mouse_images/2.png"> &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;
</p>

To check whether the system detects your hand, we print the landmark every time the system detects one
<p align="center">
<img width=40% src="virtual_mouse_images/3_final.gif"> &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;
</p>

And if the above condition states true, we proceed to mark the various landmarks on the hands and connect them. 
We do this by using the `mp.solutions.drawing_utils` (for the landmarks) and `.HAND_CONNECTIONS` (for the connections) methods.

<p align="left">
<img width=40% src="virtual_mouse_images/4afinal.gif"> &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;
<img width=40% src="virtual_mouse_images/4bfinal.gif"> &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp; 
</p>

With this, the first part of the project that is to create a hand tracking module is completed. This module can now be used as a library for various other projects.

*You can find the primitive, minimum requirements version of the model in the same repository as this.*

# Converting the had movements to mouse movements

Since we need to assign each hand gesture to perform a specific operation, we need to determine if a particular finger is straight up or down. To do that, we create a function that compares the position of the **fingertip** landmarks to the **finger joints** landmarks. If The position of the tip is lower than the joint, it means that the finger is down, and if not, it's up. 

<p align="center">
<img width=40% src="virtual_mouse_images/5final.gif"> &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;
</p>

*The list generated in the above picture is the position of the tips of all the five fingers. 1 indicates up and 0 indicates that the pertacular finger is down.'*

Now that we have our improvised hand tracking module, we start working on the virtual mouse. In addition to OpenCV and MediaPipe libraries, we also use the **AutoPy** library. It is a cross-platform GUI automation library that includes functions for controlling the keyboard and mouse.

### Pointer
We use AutoPy to control and navigate the cursor if the pointer finger is up and the rest of the other fingers are down by using `autopy.mouse.move`
<p align="center">
<img width=40% src="virtual_mouse_images/6a.jpeg"> &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;

</p>

### Click function
We use AutoPy to left-click if the pointer finger is up and the thumb is out by using `autopy.mouse.click`
<p align="center">
<img width=40% src="virtual_mouse_images/6b_final.gif"> &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;
</p>

*Similarly, we can assign many such functionalities to the model*

# Results


https://user-images.githubusercontent.com/80768666/146220853-e730c8e9-1fbb-49eb-aca4-8cb03e67583b.mp4



<p align="right" style="font-style:oblique">This model runs at 30 FPS</p>

## Refrences 

- https://google.github.io/mediapipe/
- https://pypi.org/project/autopy/
- https://docs.opencv.org/4.x/d6/d00/tutorial_py_root.html
- https://www.hindawi.com/journals/jhe/2021/8133076/
- https://www.researchgate.net/publication/347983092_Virtual_Mouse_Control_Using_Hand_Class_Gesture



