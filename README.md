# Machine Learning Assignment 2

**BITS ID:** 2026CT05154 
**Course:** Machine Learning  
**Task:** Classification Model Development and Comparison

## 1. Problem Statement

The objective of this project is to develop and compare five machine learning classification models for predicting customer churn in a telecommunications company. All models are trained and evaluated using the same stratified 80:20 train-test split and assessed using Accuracy, AUC Score, Precision, Recall, F1 Score, and Matthews Correlation Coefficient (MCC).

The models implemented are:

- Logistic Regression
- Decision Tree Classifier
- K-Nearest Neighbors (kNN)
- Gaussian Naive Bayes
- Random Forest (Ensemble)

---

## 2. Dataset Description

The Telecom Customer Churn dataset is used for this binary classification problem. The objective is to predict whether a customer will discontinue the service based on demographic, subscription, billing, and usage-related features.

| Item | Description |
|--------|------------|
| Dataset | Telecom Customer Churn Dataset |
| Instances | 50,200 |
| Target Variable | churn |
| Target Classes | 0 = Retained, 1 = Churned |
| Features | Customer demographics, subscription, billing, usage, and satisfaction attributes |
| Missing Values | Present and handled during preprocessing |
| Duplicate Records | Examined and removed where applicable |
| Train-Test Split | 80:20 Stratified |
| Random State | 42 |

### Target Variable

**churn**

- 0 → Customer Retained
- 1 → Customer Churned

### Key Features

- age
- region
- plan
- tenure_months
- monthly_charges
- total_charges
- avg_session_minutes
- sessions_last_30d
- satisfaction_score
- support_tickets_90d
- payment_failures_12m
- is_autopay

### Data Preprocessing

The following preprocessing steps were performed:

- Identified and handled missing values.
- Identified and removed duplicate records.
- Removed `customer_id` from modeling because it is only an identifier.
- Applied appropriate encoding to categorical features.
- Applied feature scaling where required.
- Used stratified train-test splitting.
- Fitted all preprocessing procedures only on training data to avoid data leakage.
- Saved the untouched test set as `test_data.csv`.

---

## 3. GitHub Repository Link

**Repository:**

`https://github.com/2026ct05154/2026CT05154-ML-Assignment-2`

---

## 4. Models Used

### Model Configurations

| Model | Configuration |
|---------|-------------|
| Logistic Regression | max_iter=3000, random_state=42 |
| Decision Tree | random_state=42 |
| kNN | n_neighbors=5, weights='distance' |
| Gaussian Naive Bayes | Default Parameters |
| Random Forest | n_estimators=300, random_state=42, n_jobs=-1 |

### Evaluation Metrics

The following metrics were used:

- Accuracy
- AUC Score
- Precision
- Recall
- F1 Score
- Matthews Correlation Coefficient (MCC)

### Model Comparison Table

*(Insert the evaluation table generated from `results_df` here.)*

| ML Model Name | Accuracy | AUC | Precision | Recall | F1 | MCC |
|--------------|----------|-----|-----------|--------|----|-----|
| Logistic Regression | | | | | | |
| Decision Tree | | | | | | |
| kNN | | | | | | |
| Naive Bayes | | | | | | |
| Random Forest (Ensemble) | | | | | | |

---

### Observations on Model Performance

| ML Model Name | Observation about model performance |
|--------------|-------------------------------------|
| Logistic Regression | Provides a strong baseline and benefits from feature scaling. |
| Decision Tree | Captures nonlinear relationships but may overfit compared to ensemble models. |
| kNN | Benefits from standardization and performs well when similar customers exhibit similar churn behavior. |
| Naive Bayes | Computationally efficient but limited by feature-independence assumptions. |
| Random Forest | Captures complex nonlinear patterns and generally provides strong and robust performance. |
| Overall Winner | Determined using F1 Score, MCC, Accuracy, and AUC Score. |

---

## 5. Execution Instructions

### Google Colab

1. Open Google Colab.
2. Upload the notebook file.
3. Upload `telecom_churn.csv`.
4. Select **Runtime → Run All**.
5. Wait for execution to complete.
6. Download all generated artifacts.

No GPU is required.

---

## 6. Generated Files

After successful execution, the following files are generated:

project-folder/

│── README.md

│── requirements.txt

│── telecom_churn.csv

│── test_data.csv

│── model/

│ ├── logistic_regression.joblib

│ ├── decision_tree.joblib

│ ├── knn.joblib

│ ├── naive_bayes.joblib

│ └── random_forest_ensemble.joblib

│── outputs/

│ ├── model_comparison.csv

│ ├── model_performance_observations.csv

│ ├── class_distribution.csv

│ ├── class_distribution.png

│ ├── all_metrics_comparison.png

│ ├── all_confusion_matrices.png

│ ├── individual confusion matrices

│ └── run_summary.json

│── screenshots/

│ └── BITS Virtual Lab execution screenshot

---

## 7. Conclusion

Five machine learning classification models were implemented and compared for customer churn prediction. Missing values, duplicate records, categorical encoding, feature scaling, and leakage-safe preprocessing were handled appropriately. All models were evaluated using Accuracy, AUC Score, Precision, Recall, F1 Score, and MCC.

The final model selection was based primarily on F1 Score and MCC, with Accuracy and AUC used as supporting metrics. The model identified in the Data-Driven Overall Winner section of the notebook is recommended as the best-performing solution for predicting customer churn on this dataset.