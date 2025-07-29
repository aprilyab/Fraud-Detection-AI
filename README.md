#  Fraud Detection Using Machine Learning

This project develops a complete end-to-end machine learning pipeline to detect fraudulent transactions using real-world-style data. It handles class imbalance, performs advanced feature engineering, builds performant models, and ensures interpretability using SHAP.

---

##  Project Structure

```
Fraud-Detection-AI/
│
├── data/ # Raw and external datasets
│ ├── Fraud_Data.csv
│ └── IpAddress_to_Country.csv
│
├── notebooks/ # Jupyter Notebooks for EDA, training, SHAP analysis
│ ├── 1_EDA.ipynb
│ ├── 2_Modeling.ipynb
│ └── 3_Explainability.ipynb
│
├── scripts/ # Python scripts for modular execution
│ ├── preprocess_data.py
│ ├── train_model.py
│ └── model_explainability.py
│
├── requirements.txt # Project dependencies
└── README.md # This file


##  Business Objective

Fraudulent transactions pose a serious threat to financial institutions and e-commerce platforms. They often occur in low-frequency patterns, making them hard to detect.

**Objective**:
- Build a deployable fraud detection system
- Improve precision and recall to minimize financial loss
- Provide interpretable decisions (especially for regulators and stakeholders)

---

##  Data Overview

### 1. `Fraud_Data.csv`

| Column Name        | Description                              |
|--------------------|------------------------------------------|
| user_id            | Unique identifier for each user          |
| signup_time        | Timestamp of account creation            |
| purchase_time      | Timestamp of the transaction             |
| purchase_value     | Value of the transaction in USD          |
| device_id          | Device identifier                        |
| source             | How user came to the site (SEO, ads...)  |
| browser            | User browser (Chrome, Firefox, etc.)     |
| ip_address         | User IP address                          |
| class              | Target (1 = Fraud, 0 = Not Fraud)        |

### 2. `IpAddress_to_Country.csv`

| Column Name        | Description                              |
|--------------------|------------------------------------------|
| lower_bound_ip_address | Starting IP range                    |
| upper_bound_ip_address | Ending IP range                      |
| country                 | Country name                        |

---

##  Data Preprocessing

- Converted `purchase_time` and `signup_time` to datetime
- Extracted:
  - **Hour**, **Weekday**, **Time Period** (Morning, Afternoon, Evening)
- Mapped IP address to country by:
  - Converting IPs to integers
  - Performing binary search on IP ranges
- Encoded:
  - **Categorical** features (e.g., `browser`, `source`, `country`)
- Scaled:
  - **Numerical** features using `StandardScaler`
- Output: `X_train`, `X_test`, `y_train`, `y_test`

---

##  Class Imbalance Strategy

Fraud data is highly imbalanced (~2.5% fraud cases).

### Techniques Explored:
- **RandomUnderSampler**
- **SMOTE (Synthetic Minority Oversampling Technique)**
- **Class weights in model**

 Final Choice: `RandomUnderSampler` — improved performance without overfitting.

---

##  Feature Engineering Highlights

| Feature Category     | Features Extracted                                      |
|----------------------|----------------------------------------------------------|
| Time-Based Features  | Hour, Weekday, Time Period                               |
| Location Features    | Country from IP                                          |
| Browser/Device       | Encoded browser types                                    |
| Behavior Features    | Signup vs purchase time difference (optional improvement) |

---

##  Machine Learning Model

###  Model Chosen: **XGBoost Classifier**
XGBoost is optimized for performance on tabular and imbalanced datasets.

###  Parameters:
- Learning Rate
- Max Depth
- Number of Estimators
- Evaluation Metric: `auc`, `logloss`

###  Evaluation Metrics:

| Metric         | Value (approx) |
|----------------|----------------|
| Accuracy       | ~97%           |
| Precision      | High           |
| Recall         | High           |
| F1-Score       | Balanced        |
| ROC AUC Score  | > 0.98         |

---

##  Evaluation Visuals

### Confusion Matrix:
![Confusion Matrix](outputs/confusion_matrix.png)

### ROC Curve:
![ROC Curve](outputs/roc_curve.png)

---

##  Explainability (SHAP)

###  Why SHAP?
- Regulatory requirements demand model transparency.
- Stakeholders need to trust model decisions.

###  SHAP Visuals:
- **Summary Plot**: Shows overall feature impact
- **Force Plot**: Explains individual prediction

| SHAP Feature Importance (Top 5) |
|---------------------------------|
| Hour of Purchase                |
| Country (from IP)               |
| Browser                         |
| Purchase Value                  |
| Source                          |

####  SHAP Summary Plot:
![SHAP Summary Plot](outputs/shap_summary_plot.png)

####  SHAP Force Plot:
![SHAP Force Plot](outputs/shap_force_plot.png)

---

##  Deployment-Readiness

-  Final Model saved using `joblib`
-  SHAP plots auto-generated on inference
-  Modular Python scripts
-  Reproducible: All steps can be re-executed using CLI or notebooks

---

##  How to Run the Project

### 1. Clone the Repo
git clone https://github.com/aprilyab/Fraud-Detection-AI.git
cd Fraud-Detection-AI

## 📝 How to Run

1. Clone the repository  
2. Install dependencies  
```bash
pip install -r requirements.txt
```
3. Run preprocessing and training
```bash
python scripts/train_model.py
```

4. Generate SHAP explanations
```bash
python scripts/model_explainability.py
```

##  Future Work

- Integrate with a real-time API
- Experiment with ensemble methods
- Add deep learning models (e.g., LSTM for time-based patterns)


📬 Contact
Author: Henok Yoseph
Email: henokapril@gmail.com
GitHub: github.com/aprilyab

🚀 This project solves real-world fraud detection problems by combining data science, domain knowledge, and explainable AI into a deployable, effective solution for fintech.

