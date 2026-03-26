# Malaria-Cell-Image-Classification-Computer-Vision-

This project investigates how different image preprocessing techniques influence the performance of a deep learning model in classifying malaria-infected blood cells. Rather than focusing only on model architecture, the analysis emphasizes how preprocessing affects feature quality and overall classification performance.

Approach

The study uses a dataset of ~27,000 blood cell images divided into two classes: parasitized and uninfected .

The workflow includes:

1. Applying multiple preprocessing techniques:
   - Otsu Thresholding
   - Canny Edge Detection
   - Combination of Otsu + Canny
2. Training a classification model using EfficientNetV2 (transfer learning)
3. Applying data augmentation to improve generalization
4. Evaluating performance using accuracy, precision, recall, F1-score, and ROC-AUC

Key insights
1. Canny preprocessing delivers the best overall performance
   - Accuracy: ~96.8%
   - AUC: ~0.98
2. Otsu shows lower performance and tends to overfit
3. The combined Otsu + Canny approach improves efficiency but does not outperform Canny alone
4. Edge-based features provide more informative patterns compared to intensity-based segmentation

Modeling details
Model: EfficientNetV2 (pretrained on ImageNet)
Data split: 70% train, 15% validation, 15% test
Optimization: AdamW with learning rate scheduling
Regularization: dropout, label smoothing, and augmentation

Why it matters

The results highlight that preprocessing plays a critical role in computer vision tasks. The choice of preprocessing method can significantly impact model performance, even when using the same architecture.

Tools: Python (PyTorch, OpenCV, EfficientNetV2)

Output

- Comparative analysis of preprocessing techniques
- Performance evaluation across multiple metrics
- Insights into accuracy vs computational trade-offs
