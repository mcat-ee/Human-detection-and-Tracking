# Human detetion and Tracking
## Introduction
_In this project we have worked on the problem of human detection,face detection, face recognition and tracking an individual. Our project is capable of detecting a human and its face in a given video and storing Local Binary Pattern Histogram (LBPH) features of the detected faces.LBPH features are the key points extracted from an image which is used to recognize and categorize images. Once a human is detected in video, we have tracked that person assigning him a label. We have used the stored LBPH features of individuals to recognize them in any other videos. After scanning through various videos our program gives output like- person labeled as subject1 is seen in video taken by camera1, subject1 is seen in video by camera2. In this way we have tracked an individual by recognizing him/her in the video taken by multiple cameras. Our whole work is based on the application of machine learning and image processing with the help of [openCV](http://opencv.org)._**This code is built on opencv 3.1.1 and python 3.4**
## Requirements
* **opencv**
	* **Installation in linux:**
			For complete installation of opencv in ubuntu you can refer [here](http://www.pyimagesearch.com/2015/06/22/install-opencv-3-0-and-python-2-7-on-ubuntu/).
	* **Installation in windows**
			For complete installation of opencv in windows you can refer [here](https://putuyuwono.wordpress.com/2015/04/23/building-and-installing-opencv-3-0-on-windows-7-64-bit/)
* **python3**
	* In Ubuntu python 3.4 can be installed via terminal with the command given below:
		`sudo apt-get install python3`
* **python libraries:**
	Here is a list of all the python dependencies 
	* Python Image Library (PIL)
	* Imutils
	* numpy

## Approach
* The code follows the steps given below:
	1. First it reads a video and process each frame one by one.
	2. For each frame it tries to detect a human. If a human is detected it draws a rectangle around it.
	3. after completing step 2 it tries to detect human face.
	4. if a human face is detected it tries to recognize it with a pre-trained model file.
	5. If human face is reocgnized it puts the label on that human face else it moves to step 2 again for next frame 
* The repository is structured as follows:
	* `main.py` : This is the main file that detects and recognizes humans.
	* 'create_face_model.py' : This python script is used to create model file using the given data in `data/` folder 
	* 'model.yaml' : This file contains trained model for given data. This trained model contains LBPH features of each and every face for given data.
	* `face_cascades/` : This directory contains sample data for testing our codes. This data is prepared by extracting face images of a praticular person from some videos.
	* `scripts/` : This directory contains some useful scripts that we used to work on different problems.

## Installation 
* To run the code you have put all the input videos in one folder and then provide the path of that folder as command line argument.
`python3 main.py /path/to/input/videos/`
* creating your own model file; just follow the steps given below to create your own model file:
	* for each individual rename the images as `subjectx.y.jpg` for example for person 1 images should be named as 'subject01.0.jpg' , `subject01.1.jpg` and so on.
	* put all the images of all the persons in a single folder then run this command given below:
		`python3 create_face_model.py /path/to/persons_images/` 

## performance of code
* Since this is a computer vision project it reqquires a lot of computation power and performance of the code is kind of an issue here.
* The code was tested on two different machines to analyse performace. The input was 30fps 720p video.
	* On a machine with AMD A4 dual-core processor we got an output of 4fps which is quite bad.
	* on a machine with Intel i5 quad-core processor we got an output of 12fps.

## Results
![alt text](https://raw.githubusercontent.com/ITCoders/Human-detection-and-Tracking/master/results/g.jpg "Logo Title Text 1")
![alt text](https://raw.githubusercontent.com/ITCoders/Human-detection-and-Tracking/master/results/k.jpg "Logo Title Text 1")
![alt text](https://raw.githubusercontent.com/ITCoders/Human-detection-and-Tracking/master/results/k.jpg "Logo Title Text 1")
![alt text](https://raw.githubusercontent.com/ITCoders/Human-detection-and-Tracking/master/results/o.jpg "Logo Title Text 1")

You can find project report [here](https://github.com/ITCoders/Human-detection-and-Tracking/raw/master/results/HUMAN%20DETECTION%20ANDaRECOGNITION.pdf)
## To do
* improve the performance of the code
* improve the accuracy of the code and reducing the false positive rate.
* improve the face recognition accuracy to over 90 percent

## Special Thanks to:
* [Jignesh S. Bhatt](http://www.iiitvadodara.ac.in/faculty/jsb001.html) - Thank you for mentoring this project
* [Kamal Awasthi](http://github.com/KamalAwasthi) - Helped in testing the code
