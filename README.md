# BCI_project_EEG_Attention
Passive BCI system for classifying focused, unfocused, and drowsy mental states from EEG using machine learning.
This repository contains code and documentation for our project on classifying human attention states using EEG data and machine learning. The project was developed as part of our CSCI 490 project at Nazarbayev University, School of Engineering and Digital Sciences.

## Project Overview

We implement a passive Brain-Computer Interface (BCI) system that distinguishes between three cognitive states:
- Focused
- Unfocused
- Drowsy

We used a publicly available EEG dataset from Inan et al. (2019), recorded during a monotonous train-driving simulation task.

## Dataset

- **Source:** [Kaggle – EEG Data for Mental Attention State Detection](https://www.kaggle.com/datasets/inancigdem/eeg-data-for-mental-attention-state-detection)
- EEG data includes 12 channels per session across 5 subjects (~25 hours of recordings)

## Methods

### Preprocessing
- Band-pass filtering (1–50 Hz)
- Standardization using `StandardScaler`
- PCA for dimensionality reduction (retain 95% variance)
- Class balancing via oversampling and weighting

### Models Implemented
- Support Vector Machine (RBF Kernel)
- Regularized Linear Discriminant Analysis (RLDA)
- Random Forest
- Logistic Regression (Ridge and Lasso)

All models were evaluated using F1-score per class and average F1-score on a held-out test set.

## Results

| Model          | Focused | Unfocused | Drowsy | Avg F1 |
|----------------|---------|-----------|--------|--------|
| RLDA           | 0.80    | 0.79      | 0.69   | 0.76   |
| Random Forest  | 0.79    | 0.75      | 0.63   | 0.72   |
| SVM (RBF)      | 0.75    | 0.72      | 0.51   | 0.66   |
| Logistic Ridge | 0.71    | 0.64      | 0.50   | 0.62   |
| Logistic Lasso | 0.70    | 0.67      | 0.52   | 0.63   |

## Authors

- Amirzhan Akhmetzhanov  
- Rauan Arstangaliyev  
- Kerbez Karipbek  
- Batyrkhan Sharipbay  
- Gulim Nurgazina

## Citation

If you use this code or results, please cite:

> Inan, C., Kaya, M., & Mishchenko, Y. (2019). Distinguishing mental attention states of humans via an EEG-based passive BCI using machine learning methods. *Expert Systems with Applications, 134*, 153–166.
