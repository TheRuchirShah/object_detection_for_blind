# object_detection_for_blind
# Abstract
Abstract
A project is basically made on object detection using deep 
learning concept the main aim of the project is to take the input 
as a image or video and exract the features and convert it into 
text and text to speech mode so that it can helpful for blind 
people 
model used in this project is YOLO[ you only look once] in order 
to extract objects and for speech conversion I’m using gTTS 
[google text to speech] and opencv for input 
I also used pydub and ffmpeg to manipulate the audio files 
generated
<br/>
<br/>
# PROBLEM STATEMENT 
I was fascinated by the idea of object detection in Computer Vision and 
wanted to start a project on it. I realized that we could probably help 
the blind “see” better using Image-to-Text and Text-to-Voice, without 
any complex hardware.
Having a complete understanding of every single piece in the whole 
pipeline is extremely difficult but I have attempted to understand as 
much as I need to know for this task
so for this project Im using YOLO model for object detection and gTTS 
for voice conversion 
<br/>
# implementation
**1. Training Data:** The model is trained with the Common Objects In Context (COCO) dataset. You can explore the images that they labeled in the link, it’s pretty cool.
<br/>**2. Model:** The model here is the You Only Look Once (YOLO) algorithm that runs through a variation of an extremely complex Convolutional Neural Network architecture called the Darknet. Even though we are using a more enhanced and complex YOLO v3 model, I will explain the original YOLO algorithm. Also, the python cv2 package has a method to setup Darknet from our configurations in the yolov3.cfg file.
I am more interested in getting something to work as soon as possible this time round so I will be using a pre-trained model. This means that COCO has already been trained on YOLO v3 by others and we have already obtained the weights stored in a 200+mb file.
If you are not sure what weights are, think of it as trying to find the Best Fit Line in Linear Regression. We need to find the right values of m and c in y=mx+c such that our line minimizes the error between all points. Now in our more complex prediction task, we have millions of Xs when we feed images into the complex network. These Xs will each have an m and these are the predicted weights stored in our yolov3.weights file. The ms have been constantly readjusted to minimize some loss function.
<br/>**3. Input Data:** We will be using our webcam to feed images at 30 frames-per-second to this trained model and we can set it to only process every other frame to speed things up.
<br/>**4. API:** The class prediction of the objects detected in every frame will be a string e.g. “cat”. We will also obtain the coordinates of the objects in the image and append the position “top”/“mid”/“bottom” & “left”/“center”/“right” to the class prediction “cat”. We can then send the text description to the Google Text-to-Speech API using the gTTS package.
<br/>**5. Output:** We will also obtain the coordinates of the bounding box of every object detected in our frames, overlay the boxes on the objects detected and return the stream of frames as a video playback. We will also schedule to get a voice feedback on the 1st frame of each second (instead of 30 fps) e.g. “bottom left cat” — meaning a cat was detected on the bottom-left of my camera view.
