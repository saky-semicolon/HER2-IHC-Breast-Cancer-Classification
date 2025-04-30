# 🧠 HER2 IHC Breast Cancer Classification using CNN & DenseNet121 with Explainable AI

This project presents a deep learning-based pipeline for classifying HER2 Immunohistochemistry (IHC) breast cancer images into four clinically relevant categories: HER2-negative (0), HER2-low (1+), HER2-borderline (2+), and HER2-positive (3+). It combines a custom Convolutional Neural Network (CNN) and transfer learning with DenseNet121, and integrates SHAP and Grad-CAM for interpretability using Explainable AI (XAI) techniques.

![image](https://github.com/user-attachments/assets/24532d11-6c34-4e7e-a159-925926cb662d)


## 📌 Project Overview

This work aims to assist pathologists in HER2 scoring by automating the classification of IHC-stained tissue images using deep learning models, reducing subjectivity and enhancing diagnostic consistency. The models were trained to recognize and classify varying HER2 expression levels using both handcrafted CNN and transfer learning.

## 🏗️ Model Architectures

### 🔹 Custom CNN
A lightweight CNN built from scratch comprising:
- 4 convolutional blocks (Conv2D + MaxPooling)
- Flatten layer
- Fully connected layers with dropout
- Softmax output layer

### 🔹 DenseNet121 (Transfer Learning)
A pre-trained DenseNet121 model fine-tuned for HER2 classification with:
- Global Average Pooling
- Custom dense layers
- Dropout regularization
- 4-class softmax output


## 🧬 Dataset Description

- **Input:** HER2 IHC-stained image patches (RGB)
- **Image Size:** Resized to 224×224
- **Classes:**
  - HER2-negative (0)
  - HER2-low (1+)
  - HER2-borderline (2+)
  - HER2-positive (3+)


## 🧼 Preprocessing & Augmentation

- **Resizing:** All images resized to 224×224
- **Normalization:** Pixel values scaled to [0, 1]
- **Augmentation Techniques:**
  - Rotation (±40°)
  - Width & height shift (20%)
  - Zoom & shear (20%)
  - Horizontal & vertical flip
  - Brightness adjustment (0.8–1.2)


## 🏋️‍♂️ Training Details

- **Batch size:** 32  
- **Epochs:** 50  
- **Loss function:** Categorical Cross-Entropy  
- **Optimizer:** Adam (LR = 0.001)  
- **Callbacks:** EarlyStopping, ModelCheckpoint  


## 🔍 Explainable AI (XAI)

### SHAP (for CNN):
- Pixel-level attribution explaining which regions most influenced model decisions.
- Visualized red/blue heatmaps indicating positive/negative contributions.

### Grad-CAM (for DenseNet121):
- Class-discriminative saliency maps showing spatial focus.
- Highlights high-activation areas correlated with HER2 expression.


## 📊 Results & Performance

| Metric        | Value          |
|---------------|----------------|
| **Test Accuracy** | 93.62%     |
| **AUC-ROC**       | High separability across all classes |

- **Confusion Matrix & ROC curves**

![image](https://github.com/user-attachments/assets/c20bf267-41b4-47f7-bc70-cc8e2b077a25)


![image](https://github.com/user-attachments/assets/dfdf5e68-2180-4d05-8d73-bf321ae391e4)


- **XAI Visualization** confirms biologically relevant focus areas

## Collaborators

| No. | Name                   |
|-----|------------------------|
| 1   | Md Serajun Nabi       |
| 2   | S M Asiful Islam Saky |
| 3   | Dema Yuden            |
| 4   | Thinley Yeshe Choden  |




