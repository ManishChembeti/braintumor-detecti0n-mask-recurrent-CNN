# braintumor-detecti0n-mask-recurrent-CNN
This project is aimed at detection of brain tumor from MRI Scan using Mask R-CNN Architecture which is the state-of-the-art architecture for object detection and object classification. It is an instance segmentation technique which automatically segments the image and generates pixel-wise masks for every input image. Along with that, Class label and bounding box is also given as an output. In this project, first steps have been taken to transfer learn the pre-trained Mask R-CNN Model on COCO dataset to the dataset consisting of brain MRI Scans.


## List of Figures:

Understanding Basic Terminology

R-CNN Architecture

Fast R-CNN Architecture

Faster R-CNN

Mask R-CNN

Visualization of Mask R-CNN process

Basic Architecture of Mask R-CNN

Process Model

Architecture of Mask R-CNN

Project Work Flow

Images in Dataset


## List of Abbreviations

MRI						Magnetic Resonance Image

R-CNN					Recurrent Convolutional Neural Network

IoU						Intersection over Union

CT						Computed Tomography

GBM						Glioblastoma Multiforme

ROI						Region of Interest

RPN						Region Proposal Network

FPN						Feature Pyramid Network

MS COCO					Microsoft Common Objects in Context

HGG						High Grade Glioma

LGG						Low Grade Glioma


## Introduction

### Objective
Imaging technology in medicine made the doctors to see the interior portions of the body for easy diagnosis. It also helped doctors to make keyhole surgeries for reaching the interior parts without really opening too much of the body. CT scanner, Ultrasound and Magnetic Resonance Imaging (MRI) took over X-Ray imaging by making the doctors to look at the body's elusive third dimension. Image processing techniques developed for analyzing remote sensing data may be modified to analyze the outputs of medical imaging systems to get best advantage to analyze symptoms of the patients with ease. 

The problem domain mainly belongs to the Segmentation part of the Fundamental Steps in Digital Image Processing whose output is generally image attributes instead of images.
The aim of the project is to take a brain MRI scan as input and predict whether tumor is present in the brain or not.

The project includes pre-processing of MRI scan which includes steps such as performing canny edge detection, erosion and dilation (morphological operations), using Mask R-CNN for instance segmentation which predicts whether the tumor is present. 

Mask R-CNN architecture is an instance segmentation method. Using Mask R-CNN, the image is automatically segmented and pixel-wise masks are constructed for every object i.e., tumor in an image, here MRI scan.

The aim of this project is to distinguish gliomas which are the most difficult brain tumors to be detected with deep learning algorithms. Because, for a skilled radiologist, analysis of multimodal MRI scans can take up to 20 minutes and therefore, making this process automatic is obviously useful.

MRI can show different tissue contrasts through different pulse sequences, making it an adaptable and widely used imaging technique for visualizing regions of interest in the human brain. Gliomas are the most commonly found tumors having irregular shape and ambiguous boundaries, making them one of the hardest tumors to detect. Detection of brain tumor using a segmentation approach is critical in cases, where survival of a subject depends on an accurate and timely clinical diagnosis.

We present a fully automatic deep learning approach for brain tumor segmentation in multi-contrast magnetic resonance image.

### Motivation

In 2018, brain tumours were ranked as the 10th most common kind of tumour among Indians. The International Association of Cancer Registries (IARC) reported that there are over 28,000 cases of brain tumours reported in India each year and more than 24,000 people reportedly die due to brain tumours annually. Brain tumour is a serious condition and can be fatal if not detected early and treated.

The incidence of central nervous system (CNS) tumors in India ranges from 5 to 10 per 100,000 population with an increasing trend and accounts for 2% of malignancies. Hospital-based databases capturing CNS malignancies had been analyzed prospectively from registrations in the neuro-oncology clinic of a tertiary care center over a period of 1 year. Astrocytomas (38.7%) were the most common primary tumors with the majority being high-grade gliomas (59.5%).

These statistics are disturbing which provided that the need of the hour is to detect brain tumor as early and accurately as possible.


### Background

Brain tumor is a group of tissue that is prearranged by a slow addition of irregular cells. It occurs when abnormal formation of cells takes place within the brain. Recently it is becoming a major cause of death of many people. The seriousness of brain tumor is very big among all the variety of cancers, so to save a life, immediate detection and proper treatment is required. Detection of these cells is a difficult problem, because of the formation of the tumor cells. It is very essential to compare brain tumor from the MRI treatment.
Simple thresholds and statistical methods are unable to adequately segment the various elements of the GBM, such as local contrast enhancement, necrosis, and edema. Most voxel-based methods cannot   achieve satisfactory results in larger data sets, and the methods based on generative or discriminative models have intrinsic limitations during application, such as small sample set learning and transfer. A new method was developed to overcome these challenges.
There are two main types of tumors: cancerous (malignant) tumors and benign tumors. Malignant tumors can be divided into primary tumors, which start within the brain, and secondary tumors, which have spread from elsewhere, known as brain metastasis tumors. This project, however, only deals with only the detection of tumor i.e. present or not present.


### Project Description and Goals

Project Description

The project involves detection of brain tumor in MRI scan using Mask R-CNN Architecture. Pre-processed data is given as input to the Mask R-CNN model, which is pre-trained on MS COCO Dataset. So, transfer learning is done and the heads of the neural network are trained with the new dataset.

Goals

1.	To accurately detect the tumor in MRI scan of brain.
2.	Return Accuracy Score and IoU (Intersection over Union)
3.	Return Bounding box around the tumor
4.	Reduce the detection time of the tumor

These are some of the major goals aimed to achieve through this project.


### Design Approach and Details

The work proposed is to detect brain tumor from MRI scans using Mask R-CNN Architecture. Using Mask R-CNN, the image is automatically segmented and pixel-wise masks are constructed for every object i.e. tumor in an image, here MRI scan.
Object detectors, such as YOLO, Faster R-CNNs, and Single Shot Detectors (SSDs), generate four sets of (x, y)-coordinates which represent the bounding box of an object in an image.
Obtaining the bounding boxes of an object is a good start but the bounding box itself doesn’t tell us anything about (1) which pixels belong to the foreground object and (2) which pixels belong to the background.
Mask R-CNN allows to generate a mask for each object in our image, thereby allowing to segment the foreground object from the background.

### Methodology and understanding

(i) Basic Difference between traditional image classification, object detection, semantic segmentation, and instance segmentation-
When performing traditional image classification our goal is to predict a set of labels to characterize the contents of an input image.
Object detection builds on image classification, but this time allows us to localize each object in an image. The image is now characterized by:
1.	Bounding box (x, y)-coordinates for each object
2.	An associated class label for each bounding box

Semantic segmentation algorithms require us to associate every pixel in an input image with a class label (including a class label for the background).
While semantic segmentation algorithms are capable of labelling every object in an image, they cannot differentiate between two objects of the same class.
This behaviour is especially problematic if two objects of the same class are partially occluding each other — we have no idea where the boundaries of one object ends and the next one begins, as demonstrated by the two purple cubes, we cannot tell where one cube starts and the other ends.

Instance segmentation algorithms, on the other hand, compute a pixel-wise mask for every object in the image, even if the objects are of the same class label i.e. it locates each pixel of every object in the image instead of the bounding boxes. It does so by using an additional fully convolutional network on top of a CNN based feature map with input as feature map and gives matrix with 1 on all locations where the pixel belongs to the object and 0 elsewhere as the output. 

The Mask R-CNN is an instance-based segmentation algorithm.

![image](https://user-images.githubusercontent.com/59841174/155372502-aa7e4556-8578-4de0-a2df-5c0062f4e4b1.png)

In order to understand Mask R-CNN let’s briefly review the R-CNN variants, starting with the original R-CNN-
Original R-CNN-

The original R-CNN algorithm is a four-step process:

•	Step 1: Input an image to the network.

•	Step 2: Extract region proposals (i.e., regions of an image that potentially contain objects) 
To solve the problem of selecting a huge number of regions, a selective search is used to extract just 2000 regions from the image and this is known as region proposals. Therefore, instead of trying to classify a large number of regions, we can just work with 2000 regions 
Therefore, Selective Search algorithm is used.
Selective search algorithm is as follows –
1. Generate initial sub-segmentation (many candidate regions)
2. Use a greedy algorithm to recursively combine similar regions
3. Use generated regions to produce the final region proposals

•	Step 3: Use transfer learning, specifically feature extraction, to compute features for each proposal (which is effectively an ROI) using the pre-trained CNN (ResNet101 Architecture).

•	Step 4: Classify each proposal using the extracted features with a Support Vector Machine (SVM).

The reason this method works is due to the robust, discriminative features learned by the CNN.

However, the problem with the R-CNN method is it’s incredibly slow. And furthermore, we’re not actually learning to localize via a deep neural network, we’re effectively just building a more advanced HOG + Linear SVM detector.

To improve upon the original R-CNN, Fast R-CNN algorithm was proposed.

![image](https://user-images.githubusercontent.com/59841174/155372674-8dd585e3-9dc7-4d15-a749-7631b82e48fd.png)
R-CNN Architecture

Fast R-CNN-

Similar to the original R-CNN, Fast R-CNN still utilizes Selective Search to obtain region proposals; however, the novel contribution from the paper was Region of Interest (ROI) Pooling module.

ROI Pooling works by extracting a fixed-size window from the feature map and using these features to obtain the final class label and bounding box. The primary benefit here is that the network is now, effectively, end-to-end trainable:

1.	We input an image and associated ground-truth bounding boxes

2.	Extract the feature map

3.	Apply ROI pooling and obtain the ROI feature vector

4.	And finally, use the two sets of fully-connected layers to obtain (1) the class label predictions and (2) the bounding box locations for each proposal.
While the network is now end-to-end trainable, performance suffered dramatically at inference (i.e., prediction) by being dependent on Selective Search.
To make the R-CNN architecture even faster we need to incorporate the region proposal directly into the R-CNN.
