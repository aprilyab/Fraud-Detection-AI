Fraud Detection AI
Accurately Detecting Fraud in E-Commerce and Banking Using Machine Learning and Explainability Tools

  Project Overview
This project develops robust machine learning pipelines to detect fraudulent transactions in e-commerce and banking environments. It tackles challenges such as class imbalance, feature engineering, and model interpretability using tools like XGBoost and SHAP. Final outputs include deployable, interpretable models to support fraud mitigation strategies at Adey Innovations Inc.

   Business Objective
To minimize financial fraud losses and enhance customer trust by:

Improving detection of fraudulent online and bank transactions.

Reducing false positives and negatives to optimize operational efficiency.

Integrating interpretable ML models into financial systems.

Supporting real-time and proactive fraud detection.

   Motivation
Fraud in digital finance is high-impact, rapidly evolving, and data-intensive. Key challenges include:

Severe class imbalance between legitimate and fraudulent cases.

Complex feature extraction from diverse data types (e.g., timestamps, IPs).

The growing demand for transparency in automated decisions.

High costs of detection errors on the user experience and business trust.

   Datasets Used
This project leverages three datasets:

1. Fraud_Data.csv (E-Commerce Transactions)
   Includes features like signup_time, purchase_time, purchase_value, device_id, etc.

   Binary label indicating fraud status.

2. IpAddress_to_Country.csv
   Maps IP address ranges to country codes.

   Enriches transactional data with geolocation features.

3. creditcard.csv (Bank Transactions)
   Contains anonymized features (V1–V28) via PCA.

   Includes Amount, Time, and binary Class label.

 All datasets exhibit significant class imbalance and require targeted preprocessing.

    Learning Outcomes
By completing this project, you will:

Integrate and preprocess structured financial and geolocation data.

Engineer temporal and spatial fraud indicators.

Apply ML models to imbalanced datasets using advanced resampling.

Evaluate using robust metrics: F1-score, AUC-PR, Confusion Matrix.

Use SHAP to interpret model predictions and communicate insights clearly.

🗂 Project Structure
fraud-detection-ai/
├── config/                  # Configuration files (e.g., config.yaml)
├── data/
│   ├── external/            # Raw auxiliary data (e.g., IP-country)
│   ├── processed/           # Cleaned datasets
│   └── raw/                 # Original datasets
├── models/                  # Trained model files
├── notebooks/
│   ├── exploratory/         # EDA notebooks
│   └── modeling/            # Training and evaluation notebooks
              # Training logs
         # Serialized best models
├── scripts/                 # Python scripts
├── src/
│   ├── data/                # Data loading & cleaning
│   ├── features/            # Feature engineering logic
│   ├── models/              # Training and inference
│   ├── utils/               # Utility functions
│   └── visualization/       # SHAP and EDA plots
├── tests/                   # Unit tests
├── visuals/                 # Custom charts and diagrams
├── .gitignore
├── README.md
└── requirements.txt
  Project Milestones
Task 1: Data Analysis & Preprocessing
Goals:

Handle nulls, data types, and duplicates.

Perform EDA (univariate & bivariate).

Merge IP geolocation data.

Engineer fraud-indicative features:

hour_of_day, day_of_week, time_since_signup

Transaction frequency, velocity

Handle imbalance (e.g., SMOTE, undersampling).

Encode categorical and scale numerical features.

Deliverables:

Preprocessing notebooks.

Visual insights.

Cleaned datasets in data/processed/.

Task 2: Model Training & Evaluation
Goals:

Prepare train-test splits for each dataset.

Train and compare:

Logistic Regression

XGBoost or Random Forest

Evaluate using:

F1-score

Precision-Recall AUC

Confusion Matrix

Deliverables:

Model training notebooks/scripts.

Saved models in models/.

Task 3: Model Explainability
Goals:

Use SHAP on the top-performing model.

Generate:

Summary plots

Force plots

Interpret top contributing features.

Link ML explanations to real-world fraud indicators.

Deliverables:

SHAP visualizations in reports/figures/

Explainability code in src/visualization/

Interpretability discussion in final report.

📬 Contact
Author: Henok Yoseph
Email: henokapril@gmail.com
GitHub: github.com/aprilyab

🚀 This project solves real-world fraud detection problems by combining data science, domain knowledge, and explainable AI into a deployable, effective solution for fintech.

