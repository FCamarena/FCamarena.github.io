---
layout: post
title: Introduction to Action Recognition
image: /img/ComputerVision.png
---

When I was a child I dreamed about a world where machines acquire "super-powers". 
Today, I'm working hard to make that dream a reality, but how?

![super machine](/img/ComputerVision.png){:class="img-responsive"}

Maybe, you have heard about Artificial Intelligence (AI), but what about Computer Vision?. That sounds a creepy thing but its only aim is to give computer eyes. 

Computer Vision has a lot of applications. Nevertheless, in this post, I'll only focus on Action Recognition, which in simple words is to determine what a subject is doing in a given video. 

![super machine](/img/CV.png){:class="img-responsive"}

This is not a trivial task (Fortunately?) but possible through  Machine Learning and Computer Vision techniques. Let's begin with a brief explanation about of what an action is. 

### Human Activity Recognition
Human Activity Recognition (HAR) can be divided into 3 levels: gestures, actions, and interactions. The basic abstraction leve is gestures that are atomic body movement. The next level are actions which are formed by a sequence of gestures and can has a specific meaning.  Finally, interactions are actions where two or more agents are involved. 

![super machine](/img/HAR.png){:class="img-responsive"}



### Highlights
- An action is a sequence of gestures with an associated meaning 
- Action Recognition can be divided into 2 main tasks: Action Recognition and Action representation
### Action recognition is divided into:
	- Global representations 
		- Not robust against occlusion, scale, rotation and lighting variability. 
		- Background subtractions is a common technique. 
	- Depth-based representations
		- It takes advantages of the camera capabilities to measure the distance between objects. 
	- **Local representations.**
		-  Local representations are the most used
		-  Use a set of descriptors that act locally on an image. 
		-  They can be divided into three steps: 
			-  Sampling
				-  Can be done: 
					-  Densely 
						-  by placing points without any semantics. 
					-  Detecting interesting points
						-  STIP
			-  Description
			-  Feature encoding
 
Briefly introduce the main approaches to represent an Action (Global Representations, Local Representations, and Depth-based)
We delved deeper into the local representations and divided them into three steps: 
Sampling
We established that the sampling step can be done in a dense manner or by locating interest points.  
We showed that the most common methods for locating interest points are:
Harris Corner Detector, Harris et al., 1988
Space-time interest points (STIP),  Laptev et al., 2005
3DSTIP, Blank et al., 2005
We also point out that a common problem in these methods is the number of points to be used and their representativeness 
Description
we stated that the description step can be done using the next methods: 
Scale-invariant feature transform (SIFT), Lowe et al., 2004
3D SIFT, Scovanner et al., 2007
Speed-up robust features (SURF),  Bay et al. 2008
3DSURF, Willems et al., 2008
HOG, Dalal et al., 2005
HOF. Dalal et al. 2006
MBH, Wang et al.  2011
We indicated that is possible to combine descriptors such as the Dense Trajectories approach. 
Feature encoding
For feature encoding we stated the existence of the following methods:
Improved Bag-of-words (BoW), Chang et al. 2017
Fisher Vector (FV), Perronnin et al. 2010
Stacked Fisher Vector (FV), Peng et al. 2014
Vector Quantization (VQ), Sivic et al., 2003
Vector of locally aggregated descriptors (VLAD), Jégou et al. 2010
Super vector encoding (SVC), Zhou et al., 2010
We categorized Action Classification in 3 approaches: Template-based, generative models and Machine learning models. We briefly define each of them. 
We highlighted that Deep-learning architectures are capable of learning representations. 
Finally, we emphasized that state-of-the-art methods focus on combining hand-crafted approaches with  deep learning features, such as the works of 
Wang et al. (2015). Action recognition with trajectory-pooled deep-convolutional descriptors.
Chéron et al. (2015) Pose-based CNN features for action recognition

