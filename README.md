# An Efficient Deep Learning Model for Bangla Handwritten Digit Recognition

## 📖 Overview

This project implements an efficient Convolutional Neural Network (CNN) to recognize handwritten Bengali digits, using a custom dataset **BHaND** (Bengali Handwritten Numerals Dataset). We closely follow the structure of MNIST (70,000 grayscale, 32×32 images) and achieve state-of-the-art accuracy with a compact model architecture and extensive benchmarking against LeNet-5, AlexNet, and MobileNetV2-0.5.

## 🚀 Features

* **Custom Dataset**

  * 70,000 samples (50k train, 10k validation, 10k test)
  * Grayscale, normalized to \[0,1], black-pixel inverted
* **Efficient CNN Architecture**

  * 4 convolutional blocks + global average pooling
  * Batch normalization, dropout, and learning-rate scheduling
* **Data Augmentation**

  * Rotation, shifts, shear, zoom
* **Training Callbacks**

  * ModelCheckpoint, ReduceLROnPlateau, EarlyStopping, custom scheduler
* **Comprehensive Evaluation**

  * Test accuracy: **99.78%**
  * Confusion matrix & classification report
* **Benchmarking**

  * Compared against LeNet5, AlexNet, MobileNetV2-0.5
  * EfficientCNN outperforms: 0.9978 vs. 0.9925 / 0.9896 / 0.9824 accuracy


## 📝 Model Architecture

* **Input:** 32×32×1
* **Conv Block 1:** 2×(Conv2D 32 → BatchNorm) → MaxPool → Dropout(0.25)
* **Conv Block 2:** 2×(Conv2D 64 → BatchNorm) → MaxPool → Dropout(0.25)
* **Conv Block 3:** 2×(Conv2D 128 → BatchNorm) → MaxPool → Dropout(0.25)
* **Conv Block 4:** 2×(Conv2D 256 → BatchNorm) → MaxPool → Dropout(0.25)
* **GlobalAveragePooling**
* **Dense 512 → BatchNorm → Dropout(0.5)**
* **Dense 256 → BatchNorm → Dropout(0.5)**
* **Output Dense 10 (softmax)**

## 📊 Results Summary

| Model            | Test Acc | Params | Latency (ms) | Size (MB) |
| ---------------- | -------- | ------ | ------------ | --------- |
| **EfficientCNN** | 0.9978   | 1.44 M | 0.72         | 16.63     |
| AlexNet          | 0.9925   | 5.69 M | 0.61         | 65.16     |
| LeNet5           | 0.9896   | 0.08 M | 0.35         | 0.99      |
| MobileNetV2-0.5  | 0.9824   | 0.72 M | 5.03         | 8.59      |



---

*Happy digit‐recognizing!*
