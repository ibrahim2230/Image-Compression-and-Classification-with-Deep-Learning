# Image-Compression-and-Classification-with-Deep-Learning

Overview

This project studies the impact of image compression on deep learning-based image classification. We use the Mini-ImageNet dataset and evaluate how different compression levels affect the performance of pre-trained convolutional neural networks.

Objectives
Apply transfer learning using pre-trained models
Implement wavelet-based image compression
Evaluate classification performance under different compression ratios
Analyze the trade-off between compression and accuracy
Dataset
Mini-ImageNet
100 classes
600 images per class (500 training, 100 testing)
Models

Two pre-trained models from PyTorch were used:

ResNet-18
MobileNetV2

Both models were fine-tuned on the Mini-ImageNet dataset.

Methodology
1. Baseline Training
Models were initialized with ImageNet pre-trained weights
Final layers were modified to classify 100 classes
Models were trained on uncompressed images
Baseline accuracy was recorded
2. Wavelet-Based Compression
Discrete Wavelet Transform (DWT) using Haar wavelet
Coefficients were thresholded to simulate compression
Three compression levels were used:
2:1 (keep 50% coefficients)
5:1 (keep 20% coefficients)
10:1 (keep 10% coefficients)
3. Evaluation
Models were tested on compressed images
Accuracy was measured for each compression level
Results were compared across models
Results
Model	Original	2:1	5:1	10:1
ResNet-18	78.37%	77.69%	61.91%	20.91%
MobileNetV2	80.39%	79.60%	56.76%	19.80%
Analysis
Light compression (2:1) has minimal impact on accuracy
Moderate compression (5:1) causes noticeable performance degradation
High compression (10:1) significantly reduces accuracy
MobileNetV2 achieves higher baseline accuracy
ResNet-18 shows better robustness at higher compression levels
Visualization

The figure below shows classification accuracy versus compression ratio for both models.

(Add your plot image here if you want)

How to Run

Open the notebook:

image_compression_classification.ipynb
Run all cells in order:
Dataset preparation
Model training
Compression
Evaluation
Ensure required libraries are installed:
PyTorch
torchvision
pywavelets
numpy
matplotlib
scikit-learn

Conclusion

Image compression affects classification performance significantly at high compression levels. There is a clear trade-off between storage efficiency and model accuracy. The results demonstrate that deep learning models rely on fine image details that are lost during aggressive compression.
