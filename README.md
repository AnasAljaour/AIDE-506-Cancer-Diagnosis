# Breast Cancer Diagnosis Multi-Model System

This project implements a comprehensive machine learning system for breast cancer diagnosis using the Wisconsin Breast Cancer dataset. The system combines Support Vector Machines (SVMs) with different kernels and ensemble methods to classify breast cell samples as either benign or malignant.

## Project Overview

The implementation focuses on:
- Data preprocessing and exploration
- SVM model implementation with various kernels
- Ensemble methods (Bagging, Random Forest, Boosting, and Voting Classifier)
- Model evaluation with performance metrics
- Model explainability using SHAP (SHapley Additive exPlanations)

## Dataset

The Wisconsin Breast Cancer dataset consists of 569 samples with 30 features extracted from digitized images of fine needle aspirates (FNA) of breast masses. Features include characteristics such as:
- Radius, texture, perimeter, area
- Smoothness, compactness, concavity
- Concave points, symmetry, fractal dimension

Each feature is computed for the mean, standard error (SE), and "worst" value for each cell nucleus.

## Implementation Details

### Data Loading and Preprocessing

- Data is loaded from a 'wdbc.data' file
- Features are standardized using StandardScaler
- Class imbalance is addressed using SMOTE (Synthetic Minority Over-sampling Technique)
- Data is split into training (80%) and testing (20%) sets

### Models Implemented

1. **SVM Models**:
   - Linear kernel SVM
   - RBF (Radial Basis Function) kernel SVM
   - Polynomial kernel SVM

2. **Ensemble Methods**:
   - Bagging with Decision Trees
   - Random Forest (bagging with feature sampling)
   - Boosting with Decision Trees
   - Voting Classifier combining all SVM models

### Evaluation Metrics

Models are evaluated using:
- Classification reports (precision, recall, F1-score)
- Confusion matrices
- Visual comparisons of model performance

### Model Performance Comparison

The system evaluates and compares the performance of all implemented models. Below is a representation of the type of comparison that would be generated by the system:

| Model | Precision | Recall | F1-Score | AUC |
|-------|-----------|--------|----------|-----|
| SVM (Linear) | 0.97 | 0.97 | 0.97 | 0.97 |
| SVM (RBF) | 0.97 | 0.97 | 0.97 | 0.97 |
| SVM (Polynomial) | 0.95 | 0.90 | 0.92 | 0.93 |
| Bagging Random Forest | 0.97 | 0.96 | 0.96 | 0.96 |
| Boosting | 0.97 | 0.96 | 0.96 | 0.96 |
| Bagging decision tree|0.95|0.94| 0.94 | 0.95
| Voting Ensemble | 0.99 | 0.98 | 0.98 | 0.98 |

The actual values are calculated during runtime by the `evaluate_models()` function and presented in classification reports. The confusion matrices visualization (`confusion_matrices.png`) provides a visual comparison of true positives, true negatives, false positives, and false negatives across all models.

For cancer diagnosis applications, both precision (minimizing false positives) and recall (minimizing false negatives) are critical metrics, as they directly impact patient outcomes and treatment decisions.

### Explainability

Model explanations are generated using SHAP to visualize:
- Feature importance through summary plots
- Waterfall plots for individual predictions
- Bar plots for feature impact on malignant predictions

## Getting Started

### Prerequisites

The code requires the following Python libraries:
- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn
- imbalanced-learn (for SMOTE)
- shap
- lime

### Running the System

Execute the main function to run the complete pipeline:

```python
python app.py
```

The execution flow:
1. Load and explore the dataset
2. Preprocess the data
3. Train SVM models
4. Train ensemble models
5. Evaluate all models
6. Generate evaluation metrics visualizations
7. Create SHAP explanations

## Output

The system generates:
- Confusion matrix visualizations saved as "confusion_matrices.png"
- SHAP explanation plots for the ensemble models
- Comprehensive evaluation metrics printed to console

## Feature Names

The 30 features used in the classification are:
- Radius_Mean, Texture_Mean, Perimeter_Mean, Area_Mean, Smoothness_Mean, Compactness_Mean, Concavity_Mean, ConcavePoints_Mean, Symmetry_Mean, FractalDimension_Mean
- Radius_SE, Texture_SE, Perimeter_SE, Area_SE, Smoothness_SE, Compactness_SE, Concavity_SE, ConcavePoints_SE, Symmetry_SE, FractalDimension_SE
- Radius_Worst, Texture_Worst, Perimeter_Worst, Area_Worst, Smoothness_Worst, Compactness_Worst, Concavity_Worst, ConcavePoints_Worst, Symmetry_Worst, FractalDimension_Worst

## Contributors
- Anas Aljaour
- Omar El Zammar.
