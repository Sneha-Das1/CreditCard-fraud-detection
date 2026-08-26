# Credit Card Fraud Detection

A machine learning project that detects potentially fraudulent credit card transactions using supervised classification algorithms and techniques for handling highly imbalanced datasets.

---

## 📌 Project Overview

Credit card fraud detection is a binary classification problem where fraudulent transactions represent only a small portion of the total transactions.

The goal of this project is to build a machine learning pipeline that can distinguish between legitimate and fraudulent transactions while focusing on metrics such as Precision, Recall, F1-Score, and ROC-AUC rather than relying only on accuracy.

The project covers the complete machine learning workflow, including data preprocessing, exploratory data analysis, feature engineering, class imbalance handling, model training, and performance evaluation.

---

## 🎯 Objectives

- Analyze and understand credit card transaction data.
- Perform data cleaning and preprocessing.
- Conduct exploratory data analysis (EDA).
- Identify patterns and characteristics of fraudulent transactions.
- Handle class imbalance using SMOTE.
- Train multiple classification models.
- Compare model performance using relevant evaluation metrics.
- Identify the most effective model for fraud detection.

---

## 🛠️ Technologies Used

### Programming Language
- Python

### Data Analysis
- Pandas
- NumPy

### Data Visualization
- Matplotlib
- Seaborn

### Machine Learning
- Scikit-learn
- Imbalanced-learn

### Development Environment
- Jupyter Notebook
- VS Code

---

## 🤖 Machine Learning Models

The project experiments with multiple classification algorithms:

### 1. Logistic Regression

Used as a baseline classification model for distinguishing fraudulent and legitimate transactions.

### 2. Decision Tree

Used to capture non-linear relationships between transaction features and fraud classification.

### 3. Random Forest

An ensemble learning algorithm used to improve classification performance by combining multiple decision trees.

---

## 🔄 Machine Learning Workflow

```text
Raw Dataset
     ↓
Data Loading
     ↓
Data Cleaning & Preprocessing
     ↓
Exploratory Data Analysis
     ↓
Feature Engineering
     ↓
Class Imbalance Analysis
     ↓
SMOTE
     ↓
Model Training
     ↓
Model Evaluation
     ↓
Model Comparison
     ↓
Fraud Prediction
