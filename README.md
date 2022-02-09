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

Project Description and Goals
Project Description
The project involves detection of brain tumor in MRI scan using Mask R-CNN Architecture. Pre-processed data is given as input to the Mask R-CNN model, which is pre-trained on MS COCO Dataset. So, transfer learning is done and the heads of the neural network are trained with the new dataset.
