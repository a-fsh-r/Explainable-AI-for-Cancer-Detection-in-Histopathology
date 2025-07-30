# Explainable AI for Cancer Detection in Histopathology

This project applies **Grad-CAM (Gradient-weighted Class Activation Mapping)** to a **ResNet-50** model trained for **binary classification** of histopathological images (cancerous vs. non-cancerous). The goal is to improve the interpretability of deep learning predictions in medical imaging.

## 🧠 Overview

While deep convolutional neural networks can achieve high accuracy in cancer detection, they often lack transparency. This project uses **Grad-CAM** to generate visual explanations by highlighting image regions that most strongly influence the model's decision — helping clinicians understand *why* a certain prediction was made.

## 🔬 Model Details

- **Architecture**: ResNet-50
- **Task**: Binary classification of breast cancer in histopathology images
- **Explainability**: Grad-CAM for visual interpretation of predictions

Grad-CAM works by using the gradients of the target class flowing into the last convolutional layer to produce a coarse localization map, highlighting **which parts of the input image contributed most to the prediction**.
