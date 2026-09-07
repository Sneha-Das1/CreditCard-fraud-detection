# 💳 Credit Card Fraud Detection

A machine learning project for detecting potentially fraudulent credit card transactions using supervised classification, exploratory data analysis, feature engineering, and techniques for handling highly imbalanced datasets.

---

## 📌 Project Overview

Credit card fraud detection is a **binary classification problem** where fraudulent transactions represent a small portion of total transactions.

The goal of this project is to build a machine learning pipeline that distinguishes between:

- **Legitimate transactions (0)**
- **Fraudulent transactions (1)**

The project focuses on handling class imbalance and evaluating models using **Precision, Recall, F1-Score, and Accuracy**, with particular attention to fraud-class recall.

The complete workflow includes:

- Data loading and preprocessing
- Exploratory Data Analysis (EDA)
- Outlier analysis and treatment
- Feature engineering
- Correlation analysis
- Class imbalance analysis
- Train/test splitting
- Feature scaling
- SMOTE-based oversampling
- Model training
- Model evaluation
- Model comparison
- Model serialization
- Fraud prediction using Streamlit

---

## 🎯 Objectives

- Analyze and understand credit card transaction data.
- Perform data cleaning and preprocessing.
- Conduct exploratory data analysis.
- Identify patterns associated with fraudulent transactions.
- Analyze legitimate vs. fraudulent transaction distribution.
- Engineer additional transaction-level features.
- Handle class imbalance using **SMOTE**.
- Train multiple classification models.
- Compare model performance using relevant classification metrics.
- Select an effective model for fraud detection.
- Deploy the trained model for transaction prediction.

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

### Model Persistence

- Joblib

### Development Environment

- Jupyter Notebook
- VS Code

### Deployment / Application

- Streamlit

---

## 📊 Dataset

The project uses a transaction-level credit card dataset containing **1,000,000 transactions** and behavioral features related to individual transactions.

### Features

| Feature | Description |
|---|---|
| `distance_from_home` | Distance of the transaction from the customer's home |
| `distance_from_last_transaction` | Distance from the previous transaction |
| `ratio_to_median_purchase_price` | Ratio of transaction amount to median purchase price |
| `repeat_retailer` | Whether the transaction occurred at a repeat retailer |
| `used_chip` | Whether a chip was used |
| `used_pin_number` | Whether a PIN was used |
| `online_order` | Whether the transaction was an online order |
| `fraud` | Target variable |

### Target Variable

- `0` → Legitimate transaction
- `1` → Fraudulent transaction

The dataset contains approximately **8.74% fraudulent transactions**, making class imbalance an important consideration during model training and evaluation.

---

## 🔍 Exploratory Data Analysis

EDA was performed to understand the structure and characteristics of the transaction data.

The analysis included:

- Missing-value analysis
- Data-type validation
- Descriptive statistics
- Feature distributions
- Class distribution analysis
- Correlation analysis
- Outlier detection

### Data Quality

All features were checked for missing values, and no missing values were found in the dataset.

### Correlation Analysis

Correlation analysis showed that `ratio_to_median_purchase_price` had the strongest positive correlation with fraud among the available features, followed by `online_order` and `distance_from_home`.

![Correlation Heatmap](CORRHEAT.png)

### Class Distribution

The dataset is highly imbalanced, with legitimate transactions significantly outnumbering fraudulent transactions.

![Class Distribution](class%20distribution.png)

### Outlier Analysis

Boxplots were used to identify potential outliers in numerical transaction features.

![Fraud Outliers](fraud%20outliers.png)

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

1. Loaded the dataset using Pandas.
2. Checked for missing values.
3. Verified feature data types.
4. Analyzed descriptive statistics.
5. Identified potential outliers.
6. Applied IQR-based outlier capping to selected numerical features.
7. Separated features and target variable.
8. Split the data into training and testing sets.
9. Applied StandardScaler to numerical/model input features.

### Outlier Treatment

IQR-based capping was applied to:

- `distance_from_home`
- `distance_from_last_transaction`
- `ratio_to_median_purchase_price`

---

## ⚙️ Feature Engineering

Additional transaction-level features were created to provide the models with more behavioral information.

### 1. Home-to-Last-Transaction Ratio

```python
home_to_last_ratio =
distance_from_home / (distance_from_last_transaction + 1e-5)
