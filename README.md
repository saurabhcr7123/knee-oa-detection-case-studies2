Automated Knee Osteoarthritis Detection and Severity Grading using Deep Learning
Overview

Osteoarthritis (OA) is a degenerative joint disease that affects millions of people worldwide and is a leading cause of disability among aging populations. Early detection and accurate grading of osteoarthritis are critical for effective treatment planning and disease management.

This project develops a deep learning-based computer vision system capable of automatically detecting and grading knee osteoarthritis from X-ray images. The system classifies radiographic images into Kellgren–Lawrence (KL) grades ranging from 0 to 4, which represent increasing levels of disease severity.

The project uses Convolutional Neural Networks (CNNs) with transfer learning based on the ResNet architecture, combined with ensemble learning to improve prediction performance. In addition, Grad-CAM visualizations are used to provide interpretability by highlighting the regions of the X-ray images that influence model predictions.

Project Objectives

The main objectives of this project are:

Develop a deep learning model for automated knee osteoarthritis classification

Train CNN models using public knee X-ray datasets

Evaluate model performance using standard classification metrics

Improve performance using ensemble learning techniques

Provide model interpretability using Grad-CAM visualizations

Dataset

The dataset used in this project is a public knee osteoarthritis dataset with Kellgren–Lawrence grading, obtained from Kaggle.

Each X-ray image is labeled according to the KL grading system, which categorizes osteoarthritis severity into five grades:

KL Grade	Description
KL0	Normal joint
KL1	Doubtful joint space narrowing
KL2	Definite osteophytes and possible narrowing
KL3	Moderate osteoarthritis
KL4	Severe osteoarthritis

Dataset structure used in this project:

kneeoa_data/
│
├── train/
├── val/
├── test/
└── auto_test/
Methodology

The overall pipeline of the proposed system consists of the following stages:

Dataset Preparation

Load knee X-ray images

Organize dataset into train, validation, and test splits

Data Preprocessing

Image resizing

Normalization

Data augmentation

Model Training

Baseline ResNet50 model using transfer learning

Improved training configurations

Ensemble Learning

Combine predictions from multiple trained models

Weighted ensemble to improve classification accuracy

Model Evaluation

Accuracy

Precision

Recall

F1-score

Confusion matrix

Model Explainability

Grad-CAM visualization of important image regions

Model Architecture

The primary deep learning model used in this project is ResNet50, a deep convolutional neural network architecture that uses residual connections to enable efficient training of deep networks.

Transfer learning with ImageNet-pretrained weights was used to improve training efficiency and performance on the medical imaging dataset.

Experimental Results

The models were evaluated on the test dataset using standard classification metrics.

Metric	Score
Accuracy	70.1%
Precision (macro)	0.70
Recall (macro)	0.71
F1 Score (macro)	0.705
Quadratic Weighted Kappa	0.85

The weighted ensemble model achieved the best performance compared to individual models.

Model Interpretability

To improve transparency of the deep learning model, Grad-CAM (Gradient-weighted Class Activation Mapping) was used to visualize the regions of the X-ray images that contribute most to the model's predictions.

Grad-CAM heatmaps show that the model focuses on the knee joint space, which is the clinically relevant region used for osteoarthritis assessment.

Project Structure
project/
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_baseline_resnet_training.ipynb
│   ├── ensemble_model_training.ipynb
│   └── gradcam_analysis.ipynb
│
├── models/
│   └── trained_model_weights/
│
├── figures/
│   └── gradcam_outputs/
│
├── report/
│   └── CaseStudy2Report.docx
│
└── README.md
Technologies Used

Python

PyTorch

torchvision

NumPy

pandas

scikit-learn

matplotlib

Google Colab

Future Improvements

Possible future extensions of this project include:

training on larger multi-institutional datasets

exploring Vision Transformer architectures

integrating automatic knee joint localization

combining imaging data with clinical patient data

References

Key research papers related to this project include:

He et al., Deep Residual Learning for Image Recognition, CVPR 2016

Selvaraju et al., Grad-CAM: Visual Explanations from Deep Networks, ICCV 2017

Kellgren & Lawrence, Radiological assessment of osteoarthritis, 1957
