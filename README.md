# Credit Card Fraud Detection

## Overview

This project focuses on detecting fraudulent credit card transactions using machine learning techniques on a highly imbalanced dataset.

The project compares multiple classification algorithms and evaluates their performance using metrics suitable for imbalanced classification.

## Dataset

The dataset contains 284,807 credit card transactions, with fraudulent transactions representing a very small proportion of the total dataset.

Due to this severe class imbalance, accuracy alone is not an appropriate metric for evaluating the model.

The dataset was obtained from Kaggle.

## Project Workflow

- Exploratory Data Analysis (EDA)
- Missing Value Analysis
- Transaction Amount and Time Analysis
- Correlation Analysis
- Class Imbalance Analysis
- Train-Test Split
- Logistic Regression Baseline
- Class Weighting
- SMOTE
- Random Forest
- LightGBM
- Feature Importance
- Hyperparameter Tuning using RandomizedSearchCV
- Final Model Evaluation

## Models Evaluated

- Logistic Regression
- Logistic Regression with Class Weighting
- Logistic Regression with SMOTE
- Random Forest
- LightGBM
- Tuned LightGBM

## Model Comparison

| Model | PR-AUC |
|---|---:|
| Logistic Regression | 0.692 |
| Logistic Regression + Class Weight | 0.672 |
| Logistic Regression + SMOTE | 0.653 |
| Random Forest | 0.796 |
| LightGBM | 0.809 |
| Tuned LightGBM | **0.830** |

## Final Model

The tuned LightGBM model achieved the best PR-AUC performance on the held-out test set.

### Test Performance

| Metric | Score |
|---|---:|
| Precision | 0.96 |
| Recall | 0.76 |
| F1-score | 0.85 |
| PR-AUC | 0.83 |

## Hyperparameter Tuning

LightGBM was optimized using RandomizedSearchCV with 3-fold cross-validation.

The selected parameters were:

```text
n_estimators = 500
learning_rate = 0.05
num_leaves = 50
min_child_samples = 20
max_depth = -1
subsample = 0.8
colsample_bytree = 0.8

Technologies Used
Python
Pandas
NumPy
Scikit-learn
LightGBM
Matplotlib
Seaborn
Jupyter Notebook
Key Findings
The dataset is highly imbalanced, making accuracy a misleading metric.
PR-AUC was used as an important evaluation metric for the fraud detection problem.
Tree-based models performed better than the initial Logistic Regression baseline.
LightGBM provided strong performance for detecting fraudulent transactions.
Hyperparameter tuning improved the LightGBM PR-AUC from 0.809 to 0.830.
