# Fairness-Aware Gender Classification Using ImageNet-Pretrained CNNs

**Repository:** CNNs_DL-Project  
**Author:** Gomathi Ramesh 

**Project Type:** Deep Learning / Fairness in Computer Vision  
**Course Project:** Ethical Implications in AI-Based Image Classification  

## Project Overview

This project analyzes ethical implications in computer vision by comparing three ImageNet-pretrained CNN models—InceptionResNetV2, EfficientNetV2, and ConvNeXt—for gender classification on face images. Beyond overall model accuracy, the project evaluates fairness across race groups using race-stratified accuracy, Demographic Parity Gap, and Equalized Odds Gap.

As part of the CNN baseline analysis, I implemented and compared three ImageNet-pretrained CNN models:

- InceptionResNetV2
- EfficientNetV2
- ConvNeXt

The models were evaluated using both utility metrics and fairness metrics to identify whether model performance differs across demographic subgroups. The fairness analysis includes race-stratified performance, Demographic Parity Gap, and Equalized Odds Gap.


## Project Goal

The main goal of this project is to examine whether CNN-based gender classification models show performance disparities across race groups, and to identify which CNN baseline provides the best balance between predictive performance and fairness.

## My Major Contributions

My major contribution to this group project focused on the **CNN baseline modeling and fairness evaluation** for gender classification.

Specifically, I:

- Implemented and compared three ImageNet-pretrained CNN baseline models:
  - InceptionResNetV2
  - EfficientNetV2
  - ConvNeXt
- Fine-tuned each ImageNet-pretrained CNN end-to-end for binary gender classification by replacing the final classification layer and updating    both the backbone and classifier weights on face image data.
- Used race as a protected attribute for subgroup-level fairness evaluation.
- Evaluated each CNN model using both utility and fairness metrics.
- Reported test accuracy, Demographic Parity Gap, and Equalized Odds Gap for each model.
- Compared the trade-off between predictive performance and fairness across the three CNN baselines.
- Identified InceptionResNetV2 as the strongest CNN baseline based on its high test accuracy and lowest Equalized Odds Gap.
- Prepared the CNN baseline results to support the later mitigation phase of the group project.

## Dataset

This project uses face images with demographic annotations, including:

- Gender: target variable for binary classification
- Race: protected attribute used for fairness evaluation
- Age group: optional metadata

Race labels are not used as the prediction target. They are used only for subgroup analysis and fairness evaluation.

## Models

### 1. InceptionResNetV2

InceptionResNetV2 combines Inception-style convolutional blocks with residual connections. It was used as one of the CNN baselines for gender classification.

### 2. EfficientNetV2

EfficientNetV2 is a newer CNN architecture designed for improved training speed and parameter efficiency. It was included to compare a more recent CNN model against other pretrained baselines.

### 3. ConvNeXt

ConvNeXt is a modernized CNN architecture inspired by design improvements from Vision Transformers while still using convolutional operations. It was included as a modern CNN baseline.

## Training Approach

Each model was initialized with ImageNet-pretrained weights and fine-tuned for gender classification.

The general training workflow included:

1. Loading the pretrained CNN backbone.
2. Replacing the final classification layer with a binary gender classification head.
3. Training the model using a supervised binary classification objective.
4. Evaluating performance on the test set.
5. Computing race-stratified fairness metrics.

## Evaluation Metrics

The project evaluates both model utility and fairness.

### Utility Metrics

- Test Accuracy
- Precision
- Recall
- F1 Score

### Fairness Metrics

- Race-stratified accuracy
- Demographic Parity Gap
- Equalized Odds Gap
- TPR and FPR differences across race groups

These metrics help determine whether the model performs consistently across demographic groups.

## Baseline Results

| Model | Test Accuracy | Demographic Parity Gap | Equalized Odds Gap |
|---|---:|---:|---:|
| InceptionResNetV2 | 0.9251 | 0.2114 | 0.1214 |
| EfficientNetV2 | 0.8517 | 0.2150 | 0.1401 |
| ConvNeXt | 0.8205 | 0.2029 | 0.1455 |

## Key Findings

Among the three CNN baselines, InceptionResNetV2 achieved the highest test accuracy and the lowest Equalized Odds Gap. ConvNeXt achieved the lowest Demographic Parity Gap, but its overall accuracy was lower compared with InceptionResNetV2.

Based on the trade-off between utility and fairness, InceptionResNetV2 was identified as the strongest CNN baseline for the next phase of the project.

## Project Structure

```text
.
├── README.md
├── notebooks/
│   ├── inceptionresnetv2_gender_classification.ipynb
│   ├── efficientnetv2_gender_classification.ipynb
│   └── convnext_gender_classification.ipynb
├── results/
│   ├── cnn_baseline_results_table.png
│   ├── fairness_metrics_summary.png
│   └── training_curves/
└── docs/
    └── project_notes.md
