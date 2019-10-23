---
layout: post
title: Introduction to Action Recognition
image: /img/ComputerVision.png
---

When I was a child I dreamed about a world where machines adquire "super-powers". 
Today, I'm working hard to make that dream a reality, but how?

![super machine](/img/ComputerVision.png){:class="img-responsive"}
Maybe, you have heard about Artificial Intelligence (AI), but what about Computer Vision?. That sound a very creepy thing but its only aims is to give a computer eyes. 

Computer Vision has a lot of application. Nevertheless, in this post, I'll only focus on Action Recognition, which in simple words is to determine what a subject is doing in a given video. Yes, like Big brother (See image 2.0)

--- A crazy ilustration about computer vision ----


This is not a trivial task (Fortunaly?) but possible through  Machine Learning and Computer Vision techniques. Let's begin with a brief explanation about what an action is. 

### Human Activity Recognition
Human Activity Recognition (HAR)[REF] can be categorized into 3 levels: Gestures, Actions and Interactions. A gesture is an atomic movement, an action is a sequence of gestures with an associated message, and interactions are actions in which two or more agents are involved. A more compresive explanation is showed in figure 3.0


--- HAR: A very simple image that explain it----- 
### Action Representation
Action Recognition is formed by 2 steps: Action representation and Action Classification. The first one is how our computer will interpreted things and the second one is how the computer manipulate theses things in order to give an answer. 

Action representation have been approached in 3 different ways: global, local and depth-based representation [REF]. Global representations have become obsolete due to high sensitivity to noise, occlusions and changing viewpoints. Depth-based representations require information about the object depth, which can be obtained by means of special cameras like Microsoft Kinect.

--- Example of Global representation ----
--- Example of depth based representation --- 

Local representations \cite{zhang2017review} are the most used and aim to describe a video through a collection of local descriptors sampled densely by placing points without any semantics or by locating points of interest. There are several approaches for  interest point location \cite{harris1988combined,laptev2005space,blank2005actions}, but one of the most widely used is the 3d space time interest points (STIP) \cite{laptev2005space}, which is an extension of the Harris detector \cite{harris1988combined}. Detecting interesting points may improve the performance, but there are some problems such as the number of points to be used and their representativeness \cite{zhang2017review}. 

Once the interest points have been identified, the next step is to describe them. The most widely used are Scale-invariant feature transform (SIFT) \cite{lowe1999object,lowe2004distinctive}, 3D SIFT \cite{scovanner20073},  speed-up robust features (SURF) \cite{bay2008speeded}, 3D SURF \cite{willems2008efficient},  HOG \cite{dalal2005histograms}, HOF \cite{dalal2006human} and  MBH \citep{wang2011action}. 

It is possible to combine several descriptors to improve performance such as the dense trajectory approach \cite{wang2013dense,wang2011action} that achieves high accuracy through the descriptors HOG, HOF, MBH, and the displacements of the trajectories (DT). Shi et al. \cite{shi2017sequential} present sequential deep trajectory descriptor (sDTD) to capture long-term motion information.

The next step is feature encoding, which the key idea is to discretize the entire space of local features extracted from a training set. Several works have been presented: Bag-of-words (BoW) \cite{chang2017improving}, fisher vector (FV) \cite{perronnin2010improving}, stacked fisher vector (SFV) \cite{peng2014action}, vector quantization (VQ) \cite{sivic2003video}, vector of locally aggregated descriptos (VLAD) \cite{jegou2010aggregating}, super vector encoding (SVC) \cite{zhou2010image}. Acording to \cite{zhang2017review} the best performance is achieved by using Dense trajectories with SFV. 

### Action Classification

Action classification \cite{zhang2017review} has been carried out using 3 main approaches: template-based, generative and discriminatory methods. Template-based methods are the simplest and obtain a result through comparisons with a pre-defined set of templates. In generative methods use probabilistic approaches and discriminative ones uses machine learning techniques like support vector machines (SVM) \cite{ng2002discriminative}, conditional Random Fields (CRF) \cite{vail2007conditional} and deep learning architectures \cite{zhang2017review}. 

On the other hand, deep learning architectures \cite{zhang2017review} like deep neural networks (DNNs) \cite{berlin2016human,huang2017deep}, convolutional neural networks (CNNs) \cite{mo2016human,simonyan2014two,li2016vlad3, gkioxari2015finding} and recurrent neural networks (RNNs) \cite{veeriah2015differential,du2015hierarchical} have achieved high accuracy values and even many of them perform the action recognition task in real time \cite{luo2018fast,zhang2016real}. Unlike traditional machine learning methods, deep neural networks has the ability to learn representations automatically.

State-of-the-art methods focuses on improving classification performance by combining CNN features with hand-crafted features. Li et al. \cite{li2016vlad3} proposed to combine CNN with VLAD to caputre mid-range and long-range dynamics. Wang et al. \cite{wang2015action} presented the deep-convolutional descriptor which combine dense trajectories with CNN features. Chéron et al. \cite{cheron2015p} introduced a Pose-based Convolutional Neural Network descriptor that proved that CNN approaches are complementary to Hand-crafted approaches.  

our work follows the path of combining CNN features with traditional methods, in our case we explore the use of CNN for the generation of interest points. 

Figure 4 sumarized all the explained:

-------------Super Figure--- 

