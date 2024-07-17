
#### PROJECT_DEMANDS.md

Create a `PROJECT_DEMANDS.md` file to detail the project requirements:

```markdown
# Project Demands: Automating Port Operations

## Overview

Marina Pier Inc. aims to leverage technology to automate port operations by creating a bias-free, corruption-free automatic reporting system to recognize different types of boats. This project involves building a Convolutional Neural Network (CNN) model and a lightweight model using transfer learning for mobile deployment.

## Objectives

1. **Build a CNN Network**:
    - Classify different types of boats.
    - Use a training and testing split of 80:20.
    - Use Keras ImageDataGenerator for data loading and normalization.
    - Train the model for 20 epochs and evaluate its performance.

2. **Build a Lightweight Model with Transfer Learning**:
    - Use a pre-trained model like MobileNetV2 for initial layers.
    - Split the dataset into 70% training and 30% testing.
    - Train the model for 50 epochs with early stopping.
    - Evaluate and compare the performance with the CNN model.

## Data Description

The dataset contains images of 9 types of boats. There are a total of 1162 images.

- **Classes**:
  - ferry_boat
  - gondola
  - sailboat
  - cruise_ship
  - kayak
  - inflatable_boat
  - paper_boat
  - buoy
  - freight_boat

## Steps to Perform

### 1. Initial Data Inspection and Cleaning

- **Check for duplicates**: Identify and remove duplicate entries.
- **Handle missing values**: Address any missing data appropriately.
- **Remove irrelevant entries**: Ensure all data points are relevant to the analysis.
- **Identify and handle outliers**: Detect and manage outliers to prevent skewed analysis.

### 2. Building CNN Model

- **Data Split**: Split the dataset into 80% training and 20% testing.
- **Data Loading**: Use Keras ImageDataGenerator with normalization (rescale=1./255).
- **Model Architecture**:
  - Conv2D layers with ReLU activation.
  - MaxPooling layers.
  - GlobalAveragePooling2D layer.
  - Dense layers with ReLU and softmax activation.
- **Compilation**: Use Adam optimizer and categorical cross-entropy loss.
- **Training**: Train the model for 20 epochs.
- **Evaluation**: Evaluate the model on test images and generate confusion matrix and classification report.

### 3. Building Transfer Learning Model

- **Data Split**: Split the dataset into 70% training and 30% testing.
- **Data Loading**: Use Keras ImageDataGenerator with normalization (rescale=1./255).
- **Model Architecture**:
  - Use MobileNetV2 as the base model.
  - GlobalAveragePooling2D layer.
  - Dropout and Dense layers with ReLU activation.
  - BatchNormalization layers.
  - Dense layer with softmax activation.
- **Compilation**: Use Adam optimizer and categorical cross-entropy loss.
- **Training**: Train the model for 50 epochs with early stopping.
- **Evaluation**: Evaluate the model on test images and plot training/validation loss and accuracy.

## Conclusion

This project aims to automate port operations by leveraging deep learning techniques to recognize different types of boats. By building and comparing CNN and transfer learning models, we aim to deploy a robust and efficient solution for mobile devices.
