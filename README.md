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


1- Introduction

1.1. Objective
Imaging technology in medicine made the doctors to see the interior portions of the body for easy diagnosis. It also helped doctors to make keyhole surgeries for reaching the interior parts without really opening too much of the body. CT scanner, Ultrasound and Magnetic Resonance Imaging (MRI) took over X-Ray imaging by making the doctors to look at the body's elusive third dimension. Image processing techniques developed for analyzing remote sensing data may be modified to analyze the outputs of medical imaging systems to get best advantage to analyze symptoms of the patients with ease. 

The problem domain mainly belongs to the Segmentation part of the Fundamental Steps in Digital Image Processing whose output is generally image attributes instead of images.
The aim of the project is to take a brain MRI scan as input and predict whether tumor is present in the brain or not.

The project includes pre-processing of MRI scan which includes steps such as performing canny edge detection, erosion and dilation (morphological operations), using Mask R-CNN for instance segmentation which predicts whether the tumor is present. 

Mask R-CNN architecture is an instance segmentation method. Using Mask R-CNN, the image is automatically segmented and pixel-wise masks are constructed for every object i.e., tumor in an image, here MRI scan.

The aim of this project is to distinguish gliomas which are the most difficult brain tumors to be detected with deep learning algorithms. Because, for a skilled radiologist, analysis of multimodal MRI scans can take up to 20 minutes and therefore, making this process automatic is obviously useful.

MRI can show different tissue contrasts through different pulse sequences, making it an adaptable and widely used imaging technique for visualizing regions of interest in the human brain. Gliomas are the most commonly found tumors having irregular shape and ambiguous boundaries, making them one of the hardest tumors to detect. Detection of brain tumor using a segmentation approach is critical in cases, where survival of a subject depends on an accurate and timely clinical diagnosis.
We present a fully automatic deep learning approach for brain tumor segmentation in multi-contrast magnetic resonance image.
