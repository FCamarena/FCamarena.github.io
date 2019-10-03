---
layout: post
title: Introduction to Action Recognition
# image: /img/hello_world.jpeg
---

When I was a child I dreamed about a world where machines adquire "super-powers" (See image 1.0). 
To day, I'm working hard to make that dream a reality... but how?

---- A draw of a Super Machine ---- 

May be, you have heard about Artificial Intelligence (AI), but what about Computer Vision?. That sound a very creepy thing but its only aims is to give a computer eyes. 

Computer Vision has a lot of application. Nevertheless, in this post, I'll only focus on Action Recognition, which in simple words is to determinme what a subject is doing in a given video. Yes, like Big brother (See image 2.0)

--- A crazy ilustration about computer vision ----


This is not a trivial task (Fortunaly?) but possible through  Machine Learning and Computer Vision techniques. Let's begin with a brief explanation about what an action is. 


Human Activity Recognition (HAR)[REF] can be categorized into 3 levels: Gestures, Actions and Interactions. A gesture is an atomic movement, an action is a sequence of gestures with an associated message, and, interactions are actions in which two or more agents are involved. A more compresive explanation is showed in figure 3.0

--- HAR: A very simple image that explain it----- 

Action Recognition is formed by 2 steps: Action representation and Action Classification. The first one is how our computer will interpreted things and the second one is how the computer manipulate theses things in other to give an answer. 

Action representation have been approaches in 3 different ways: Global, local and depth-based representation [REF]. Global representations have become obsolete due to high sensitivity to noise, occlusions and changing viewpoints. Depth-based representations require information about the object depth, which can be obtained by means of special cameras like Microsoft Kinect.

--- Example of Global representation ----
--- Example of depth based representation --- 

Local representations [REF ]have been the most used and aim to describe a video through a collection of local descriptors sampled densely or by locating points of interest. Then, local features are combined by a feature encoding approach. 

--- Example of Local representation ----


Interest points detection seeks for key elements of the video-frame, compared to dense sampling that places points without any semantics.  There are several approaches [REF] 
that have been used to locate these key points, but one of the most widely used is the 3d space time interest points (STIP) [REF], which is an extension of the Harris detector [REF].  

Detecting interesting points permits to achieve remarkable performance, but one of the common problems[REF] is finding a stable amount of points. Also, many of them can be false alarms. 
 
Once the points are sampled, the next step is to describe them. Scale-invariant feature transform (SIFT) proposed by Lowe et al.[REF] is widely used due to its robustness to noise, lighting changes, viewpoint changes and its scale and rotation invariance [REF]. A extended 3D version is presented by Scovanner et al [REF].

The speed-up robust features (SURF) [REF] is another acknowledged approach for its efficiency. An extended 3D version is presented in [REF].  


Dense trajectories is another well-know approach used is the dense trajectories [REF] approach that achieves high performance through the descriptors HOG [REF], HOF [REF], MBH [REF],and the displacements of the trajectory (DT)[REF]. Shi et al. [REF] present sequential deep trajectory descriptor [REF] to capture long-term motion information.

The next step is feature encoding, which  the key idea is to discretize the entire space of local features extracted from a training set. Bag-of-words (BoW)[REF], fisher vector (FV) [REF], stacked fisher vector (SFV) [REF], vector quantization (VQ) [REF], vector of locally aggregated descriptos (VLAD) [REF], super vector encoding (SVC) [REF]. Acording to [REF] the best performance is achieved by using Dense trajectories with SFV. 

Action classification has been performed through diverse approaches [REF], but discriminative methods are the most commonly used. support vector machines (SVM) [REF], conditional Random Fields (CRF)[REF] and deep learning architectures [REF] are examples of them. 


On the other hand, deep learning architectures \cite{zhang2017review} like deep neural networks (DNNs)[REF], convolutional neural networks (CNNs) [REF] and recurrent neural networks (RNNs) [REF] have achieved high accuracy values and even many of them perform the action recognition task in real time [REF]. Unlike traditional machine learning methods, deep neural networks has the ability to learn representations automatically.

Current research focuses on improving classification performance by combining CNN features with hand-crafted features. Li et al. [REF] proposed to combine CNN with VLAD to caputre mid-range and long-range dynamics. Wang et al.[REF] proposed  the deep-convolutional descriptor which combine dense trajectories with CNN features. Chéron et al. [REF] proposed a Pose-based Convolutional Neural Network descriptor and demonstrate that  CNN approaches are complementary to Hand-crafted approaches like dense trajectories.  


Figure 4 sumarized all the explained:

-------------Super Figure--- 

