# credit-card-fraud-detection
A comparative study of Decision Tree and Linear SVM for credit card fraud detection.
#   Credit Card Fraud Detection (Decision Tree & Linear SVM)

This project is a binary classification task to detect fraudulent credit card transactions using Decision Tree and Linear SVM classifiers. The dataset used is highly imbalanced, and model performance is evaluated using ROC-AUC, classification reports, and confusion matrices.

---

##   Dataset

The dataset used is a public dataset from Kaggle, accessed via IBM's cloud:

- Source: `https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-ML0101EN-SkillsNetwork/labs/Module%203/data/creditcard.csv`
- Binary target variable:  
  - `0`: Non-fraud  
  - `1`: Fraud

---

##   Steps Overview

### 1. Data Loading & EDA
- Loaded CSV data using `pandas`
- Performed:
  - Info summary
  - Descriptive stats
  - Missing values check
  - Class distribution plot (pie chart)
  - Feature correlation with target (`Class`)

### 2. Feature Selection & Preprocessing
- Selected top 6 features most correlated with `Class`
- Standardized the features
- Applied L2 normalization

### 3. Train-Test Split
- Used `train_test_split` with 30% test size

### 4. Sample Weighting
- Computed `sample_weight` using `compute_sample_weight` for class imbalance handling

---

##   Models Used

###   Decision Tree Classifier
- Hyperparameter tuning using `GridSearchCV`
  - `max_depth`: [2, 4, 6, 8, 10]
  - `min_samples_split`: [2, 5, 10]
  - `criterion`: ['gini', 'entropy']
- Used `sample_weight` during training
- Evaluated with:
  - ROC Curve
  - Confusion Matrix
  - Classification Report

###   Linear SVM Classifier
- Used `LinearSVC` with:
  - `class_weight='balanced'`
  - `loss='hinge'`
- Evaluated using:
  - Decision function (`.decision_function`)
  - ROC Curve
  - Confusion Matrix
  - Classification Report

---

##   Evaluation Metrics

- ROC-AUC score (printed)
- ROC Curve visualization
- Confusion Matrix with `ConfusionMatrixDisplay`
- Classification report from `sklearn.metrics`

---

##   How to Run

Just run the Python script:

```bash
python your_script_name.py
---

##   Author
Zahra
