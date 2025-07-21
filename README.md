# Fraud Detection AI

**Accurately Detecting Fraud in E-Commerce and Bank Transactions Using Machine Learning and Explainability Tools**


##  Project Overview

This project aims to build robust machine learning pipelines for fraud detection in **e-commerce** and **bank transactions**. The project addresses challenges like **data imbalance**, **feature engineering**, and **explainability** using tools such as **XGBoost** and **SHAP**. Final deliverables include interpretable models and comprehensive analysis to assist fraud prevention strategies at **Adey Innovations Inc.**

---

##  Business Objective

To reduce financial losses and enhance customer trust by:

- Improving fraud detection in online transactions and banking.
- Reducing false positives and false negatives.
- Integrating interpretable machine learning models into financial systems.
- Supporting real-time detection and proactive decision-making.

---

##  Motivation

Financial fraud is complex, fast-evolving, and costly. Challenges include:

- Vast imbalance between fraudulent and legitimate transactions.
- Difficulties in feature extraction from diverse data (timestamps, IPs).
- The need for transparency and trust in automated systems.
- Impact of detection accuracy on user experience.

---

##  Dataset Description

The project utilizes three main datasets:

### 1. `Fraud_Data.csv` (E-commerce Transactions)
- Includes transaction details and a binary fraud label.
- Features: `signup_time`, `purchase_time`, `purchase_value`, `device_id`, etc.

### 2. `IpAddress_to_Country.csv` (Geolocation)
- Maps IP ranges to country codes.
- Used to enrich e-commerce transaction data.

### 3. `creditcard.csv` (Bank Credit Transactions)
- Contains anonymized PCA components (`V1`–`V28`), `Amount`, `Time`, and `Class` as label.

>  All datasets have class imbalance requiring special preprocessing.

---

##  Learning Outcomes

- Handle structured financial data and merge external features.
- Engineer time and location-based fraud detection signals.
- Apply ML models to imbalanced datasets.
- Use evaluation metrics like AUC-PR and F1-Score.
- Interpret model predictions with SHAP explainability.

##  Project Folder Structure


fraud-detection-ai/
├── config/
│   └── config.yaml
├── data/
│   ├── external/
│   ├── processed/
│   └── raw/
├── models/
├── notebooks/
│   ├── exploratory/
│   └── modeling/
├── reports/
│   ├── figures/
│   └── logs/
├── saved_models/
├── scripts/
├── src/
│   ├── data/
│   ├── features/
│   ├── models/
│   ├── utils/
│   └── visualization/
├── tests/
├── visuals/
├── .gitignore
├── README.md
└── requirements.txt

## Deliverables and Tasks

### Task 1: Data Analysis and Preprocessing

#### Objectives:

- Handle missing values and data types
- Remove duplicates
- Perform EDA: univariate and bivariate analysis
- Merge IP data to enable geolocation features
- Feature engineering:
  - `hour_of_day`, `day_of_week`, `time_since_signup`
  - Transaction frequency and velocity metrics
- Handle class imbalance
- Normalize/scale numeric features
- Encode categorical variables

#### Deliverables:

- Jupyter notebooks for preprocessing
- Visualizations and insights
- Cleaned and transformed datasets saved in `data/processed/`

---

### Task 2: Model Building and Training

#### Objectives:

- Train-test split for both datasets
- Build two models per dataset:
  - **Logistic Regression**
  - **XGBoost** or **Random Forest**
- Evaluate using:
  - **F1-score**
  - **Precision-Recall AUC**
  - **Confusion Matrix**

#### Deliverables:

- Model training scripts in `src/models/`
- Evaluation plots in `reports/figures/`
- Saved models in `saved_models/`
- Decision justification report


### Task 3: Model Explainability

#### Objectives:

- Apply **SHAP** to best-performing model
- Generate:
  - **SHAP summary plot**
  - **Force plot**
- Interpret key feature contributions
- Link SHAP explanations to business insights

#### Deliverables:

- SHAP visualizations in `reports/figures/`
- SHAP implementation script in `src/visualization/`
- Final report discussion on interpretability


## Contact
**Author**: Henok Yoseph (henokapril@gmail.com)
**Email**: henokapril@gmail.com  
**GitHub**: https://github.com/aprilyab


This project is  designed to solve real-world fintech challenges by combining structured analysis, advanced ML techniques, and explainability into a practical, deployable solution.

