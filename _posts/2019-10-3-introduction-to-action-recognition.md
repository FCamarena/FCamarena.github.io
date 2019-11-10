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

### Action Recognition 

Now, that we know what is an actions, lets review how can we recognize actions. This process is divided into 2  substasks: Action representation and Action Recognition. 

#### Action Representation

Action representation is the way the computer interprets an image. There is 3 main groups: global, local and depth-based representations.

Global representations extract from a video a single global feature. A common technique used is background subtraction to obtain a subject-silhouette. This types of representations are not longer used because the high sensitivity to noise, conclusions and rotation-scale perspectives. 

Depth-based approaches take advantage of the capability to measure distances and object depths of special cameras, like Microsoft Kinect. Depth maps and skeleton-based representations are common approaches in this representation. 

Finally, local representations use a collection of descriptors applied locally to a set of points. This methods are widely used tanks to its robustness to noise and partial occlusions. 

![super machine](/img/AR.png){:class="img-responsive"} 

Let’s go deeper with local representation. To achieve it we need to perform 3 steps: sampling, description and encoding. 
Sampling can be by placing points densely (without any semantic) or by locating points of interest. The most common for points location are space-time interest points (STIP), 3D space-time interest points (3DSTIP) and Harris corner detector. Finding points of interest may improve the classification performance, but there are some problems associated with parameters used as the number de points to be located and its representativeness. 

The next step is to describe the video at the position desired. Some widely used methods are Scale-invariant feature transform (SIFT), 3D Scale-invariant feature transform (3DSIFT), speed-up robust features (SURF), 3D speed-up robust features (3DSURF), histogram of oriented gradients (HOG), histogram of oriented flow (FLOW), motion boundary descriptors (MBH), and trajectories displacements (DT). We can combine as many descriptors as we want to improve classification performance, for example, Improved Dense Trajectories implements HOG, HOF, MBH and trajectories displacements to classify actions. 


Feature encoding aims to discretize the space of local features extracted from the training set. Common methods are bag-of-words (BoW), fisher vector (FV), stacked fisher vector (SFV), vector quantization (VQ), vector of locally aggregated descriptors (VLAD) and super vector encoding (SVC). SFV proved to be a excellent option for this problem. 

This techniques are know as handcrafted features. Nevertheless, recent works are implemented convolutional neural network features that are learned automatically. 

##### Action Classification 

As action representation, action classification has been performed by 3 main approaches: template-based, generative and discriminative models. 

Template-based are the simplest one. In this method we have a predefined set of templates that we use to find the most similar to the descriptor to be classified. 

Generative models are based on probability and statistic techniques. Within this models we found classic bayesian Networks and Markova chains. 

Finally, discriminative models implement machine learning techniques like support vector machines (SVM), conditional random fields (CFR), deep neural networks (DNNs), convolutional neural networks (CNNs), and recurrent neural networks (RNNs). Unlike traditional machine learning methods, deep learning architectures can learn representations by itself. 

##### State of the art

State-of-the-art methods focus on improving classification accuracy by combining CNN features with hand-crafted features. Some highlighted methods are the one of Li et al. that proposed to combine CNN with VLAD to capture mid-range and long-range dynamics, the one of  Wang et al. which introduced the deep-convolutional descriptor that combines dense trajectories with CNN features. Also, Chéron et al. introduced a Pose-based Convolutional Neural Network descriptor that proved that CNN approaches are complementary to hand-crafted approaches. 


### conclusions

Action recognition is active field with ongoing developments. Up to now, we divide it in two tasks: action representation and action classification where local representations and machine learning techniques are the most used respectively. 

State-of-the-art methods combine handcrafted features with CNN ones. The next figure summarize the explained. 

![super machine](/img/Summary.png){:class="img-responsive"} 

