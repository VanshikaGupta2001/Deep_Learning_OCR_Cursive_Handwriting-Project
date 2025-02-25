# Deep Learning OCR Model for Cursive Handwritten Data

This project focuses on building a **Deep Learning Optical Character Recognition (OCR)** model capable of recognizing cursive handwritten text. The model is designed to handle challenges such as variations in handwriting styles, deformations, and noise. The project leverages the **IAM On-Line Handwriting Words Database (IAM-OnDB)** and implements advanced deep learning architectures like **CNN-BiLSTM**, **CNN-BiGRU**, and **CRNN**.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Problem Statement](#problem-statement)
3. [Dataset](#dataset)
4. [Project Objectives](#project-objectives)
5. [Models Implemented](#models-implemented)
6. [Methodology](#methodology)
7. [Results](#results)
8. [Usage](#usage)

---

## Introduction
Optical Character Recognition (OCR) is a technique used to extract textual information from digital or scanned documents without human intervention. Handwritten text recognition is particularly challenging due to variations in writing styles, deformations, and noise. This project aims to build a robust OCR model using deep learning techniques to recognize cursive handwritten text.

---

## Problem Statement
Handwritten characters are more difficult to recognize than printed characters due to differences in writing styles, deformations, incomplete strokes, and noise. This project addresses the challenge of recognizing cursive handwritten text using deep learning models.

---

## Dataset
The **IAM On-Line Handwriting Words Database (IAM-OnDB)** is used for this project. It contains:
- **115,320 isolated and labeled words**
- **221 writers** contributing handwriting samples
- **10,257 isolated and labeled text lines**
- **86,272 word instances** from a 11,059-word dictionary

---

## Project Objectives
1. **Text Recognition**: Convert cursive handwritten text into editable digital format.
2. **Applications**:
   - Recognize medicine names from doctors’ prescriptions.
   - Historical document recognition.
   - Automatic reading of bank cheques.
   - Real-time handwriting-to-text conversion.
   - Data extraction from filled forms.

---

## Models Implemented
1. **CRNN (Convolutional Recurrent Neural Network)**:
   - Combines CNN for feature extraction and RNN for sequence modeling.
   - **Accuracy**: 31.27%
   - **Edit Distance**: 19.7801

2. **CNN-BiLSTM (CNN + Bidirectional LSTM)**:
   - Uses CNN for spatial feature extraction and BiLSTM for sequence modeling.
   - **Accuracy**: 78.16%
   - **Edit Distance**: 17.8539

3. **CNN-BiGRU (CNN + Bidirectional GRU)**:
   - Uses CNN for spatial feature extraction and BiGRU for sequence modeling.
   - **Accuracy**: 76.39%
   - **Edit Distance**: 17.9604

---

## Methodology
### Data Engineering
1. **Data Ingestion**: Load the IAM-OnDB dataset.
2. **Exploration and Validation**: Analyze dataset metadata and validate data quality.
3. **Data Wrangling**: Preprocess images (padding, resizing, noise removal).
4. **Data Labeling**: Assign labels to each image.
5. **Data Splitting**: Split data into training, validation, and test sets.

### Model Engineering
1. **Model Training**: Train models using **Adam optimizer** and **CTC loss**.
2. **Model Evaluation**: Evaluate models using accuracy and edit distance.
3. **Model Testing**: Test models on unseen data.
4. **Model Packaging**: Export models for deployment.

### Model Deployment
1. **Model Serving**: Deploy models in a production environment.
2. **Performance Monitoring**: Monitor model performance on live data.
3. **Performance Logging**: Log inference results for analysis.

---

## Results
### Performance Metrics
| Model          | Edit Distance | Accuracy | Loss  | Validation Loss |
|----------------|---------------|----------|-------|-----------------|
| CRNN           | 19.7801       | 31.27%   | 9.220 | 8.648           |
| CNN-BiLSTM     | 17.8539       | 78.16%   | 3.898 | 3.104           |
| CNN-BiGRU      | 17.9604       | 76.39%   | 4.318 | 3.610           |

### Key Findings
- **CNN-BiLSTM** achieved the highest accuracy (78.16%) and lowest edit distance (17.8539).
- **CRNN** struggled with longer words due to vanishing gradients.
- **CNN-BiGRU** performed slightly worse than CNN-BiLSTM but was faster to train.

---

## Usage
### Prerequisites
- Python 3.x
- TensorFlow/Keras
- NumPy, Pandas, Matplotlib, Seaborn
