# Explainable AI for Cancer Detection in Histopathology

This project applies **Grad-CAM (Gradient-weighted Class Activation Mapping)** to a **ResNet-50** model trained for **binary classification** of histopathological images (cancerous vs. non-cancerous). The goal is to improve the interpretability of deep learning predictions in medical imaging.

## 🧠 Overview

While deep convolutional neural networks achieve high accuracy in cancer detection, their decision-making process is often considered a "black box." To address this, **Grad-CAM (Gradient-weighted Class Activation Mapping)** is applied to provide visual explanations by highlighting the most important regions in the image influencing the model's prediction.

Mathematically, Grad-CAM computes the importance weights for each feature map in the last convolutional layer by averaging the gradients of the predicted class score \( y^c \) with respect to the feature map activations \( A^k \):

\[
\alpha_k^c = \frac{1}{Z} \sum_i \sum_j \frac{\partial y^c}{\partial A_{i,j}^k}
\]

where:

- \( \alpha_k^c \) is the importance weight of feature map \( k \) for class \( c \),
- \( A_{i,j}^k \) is the activation at spatial location \((i,j)\) in feature map \( k \),
- \( Z \) is the number of spatial locations (i.e., \( i \times j \)).

The final Grad-CAM heatmap \( L_{\text{Grad-CAM}}^c \) is computed as a weighted combination of the feature maps followed by a ReLU:

\[
L_{\text{Grad-CAM}}^c = \text{ReLU} \left( \sum_k \alpha_k^c A^k \right)
\]

This heatmap highlights the regions in the input image that have the most positive influence on the model's prediction for class \( c \), thus improving interpretability and trust in AI-assisted cancer detection.


## 🔬 Model Details

- **Architecture**: ResNet-50
- **Task**: Binary classification of breast cancer in histopathology images
- **Explainability**: Grad-CAM for visual interpretation of predictions

Grad-CAM works by using the gradients of the target class flowing into the last convolutional layer to produce a coarse localization map, highlighting **which parts of the input image contributed most to the prediction**.
