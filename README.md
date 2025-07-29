# Lab 3 — FMLF: Vanilla CNN and Fine-Tuned VGG16

This notebook explores image classification using deep learning, focusing on the Dogs vs Cats dataset from Kaggle. The goal was to compare two approaches:

Transfer Learning using a pre-trained VGG16 model

A Custom-built Convolutional Neural Network (CNN) trained from scratch

I use a balanced subset of 5,000 images (2,500 cats and 2,500 dogs), perform exploratory data analysis (EDA), train and evaluate both models, and analyze performance issues through failure case inspection.

After training both models and using the validate subset to validate the models, I used the test dataset to test both of these models. In the end I make a comparison of both models and determine which of them performs better.

## Steps Performed

### 1. Data Collection
Downloaded and extracted dataset from Kaggle.

Verified a balanced class distribution: 2,500 images for each class.

### 2. Exploratory Data Analysis (EDA)
Counted images per class.

Visualized random samples of cat and dog images.

Analyzed image dimensions and aspect ratio distributions.

Checked for corrupted or unreadable images.

### 3. Cleaning & Preprocessing
Removed corrupted images.

Skipped resizing to preserve image quality.

Skipped duplicate removal since no duplicates were detected.

### 4. Modeling
Model 1: VGG16 (Transfer Learning)

Fine-tuned on our dataset.

Faster convergence and better generalization.

Model 2: Custom CNN

Built from scratch with Conv2D and MaxPooling layers.

Required more epochs to converge.

### 5. Evaluation
Both models were evaluated on:

Accuracy

Precision & Recall

Confusion Matrix

Failure cases (misclassified images)
## Conclusions:

We tested two models on 2,000 images (1,000 cats and 1,000 dogs): a custom-built CNN and a fine-tuned VGG16. The results were clear — VGG16 outperformed the custom model across the board.

### What We Learned?

VGG16 reached 90% accuracy, while the custom CNN got 77%.

VGG16 was more consistent, showing strong precision, recall, and F1-scores for both cats and dogs.

This is largely thanks to transfer learning — VGG16 was pre-trained on a huge dataset (ImageNet), giving it a strong ability to recognize patterns even in new tasks.

The custom CNN did better than expected, but its simpler architecture couldn’t match the depth and feature power of VGG16.

Most of the custom model’s mistakes were in borderline cases — for example, images with confusing angles or poor lighting.

### Bottom Line
This project showed how deep, pre-trained models like VGG16 can dramatically improve performance, especially in image classification problems. While building your own CNN from scratch is a great learning exercise, real-world applications benefit a lot from leveraging proven architectures.

All large files (datasets and models) are tracked using [DVC (Data Version Control)](https://dvc.org/) for efficient versioning and reproducibility.



