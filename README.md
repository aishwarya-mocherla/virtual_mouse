
# **AI VIRTUAL MOUSE**
The aim of this project is to develope a system that will allow the user to control their computer cursor using their fingertips and  different hand gestures.

#### This project is divided into two parts :
- Developing a hand tracking module
- Using the module to develope the virtual mouse 

# Hand Tracking module 
The main objective of creating this modlule is to set a base algorithm to use for all the necessary hand and gesture related projects.

**MediaPipe** is a framework developed by google that constist of various models that allows us to work with various fundamental AI problems, such as face detection, moving object tracking, object detection, and a lot of other issues that revolve around the various key points or landmarks of an object.

The model we are working with for this project is the hand tracking model. 

It uses two main modules at the backend :
- Palm Detection: provides a cropped image of the hand

**_picture of cropped hand 1 _**

- Hand Landmarks: detects the various Landmarks / keypoints of the hand

**_picture of all the hand key points 2 _**

The hand consists of 21 different landmarks which are listed below:

- WRIST 0                              
- THUMB_CMC 1
- THUMB_MCP 2                           
- THUMB_IP 3
- THUMB_TIP 4                           
- INDEX_FINGER_MCP 5
- INDEX_FINGER_PIP 6                    
- INDEX_FINGER_DIP 7
- INDEX_FINGER_TIP 8                    
- MIDDLE_FINGER_MCP 9
- MIDDLE_FINGER_PIP 10                  
- MIDDLE_FINGER_DIP 11
- MIDDLE_FINGER_TIP 12                  
- RING_FINGER_MCP 13
- RING_FINGER_PIP 14                    
- RING_FINGER_DIP 15
- RING_FINGER_TIP 16                    
- PINKY_MCP 17
- PINKY_PIP 18                         
- P INKY_DIP 19
- PINKY_TIP 20


To check whether the system detects your hand, we print the landmark every time the systems detects one

**_video of printed landmark 3_**

And if the above condition states through, we proceed to marking the various landmarks on the hands and connect them. 
We do this by using the "mp.solutions.drawing_utils" (for the landmarks) and .HAND_CONNECTIONS (for the connections) methods.

**_photo of dots 4a_**
**_photos of dots and lines 4b_**

Now that our main hand tracking model with its minimum needed requirements is ready , we convert this hard coded program to various classes to turn it into an object oriented program. 

With this, the first part of the project that is to create an hand tracking module is completed. This module can now be used as a library for various other projects.


# Developing the virtual mouse

Before we move on to developing the main model, we need to improvise our hand tracking module according to our necessities.

These are the following additions made to the model :

Now that we have our updated hand tracking module, we start with virtual mouse. In addition to OpenCV and MediaPipe libraries, we also use the **AutoPy** library. It is a cross-platform GUI automation library that includes functions for controlling the keyboard and mouse.