# 📊 Credit Risk Score Prediction Project

## 🔍 Overview
This project aims to predict credit risk scores based on various financial and demographic features. The goal is to build a robust regression model that accurately estimates the creditworthiness of individuals, helping lenders make informed decisions.

---
The workflow includes:
- **Data loading and cleaning**
- **Multicollinearity detection using VIF**
- **Model training and hyperparameter tuning**
- **Model evaluation using MSE, RMSE, and R² score**

Multiple models were evaluated — **Ridge Regression**, **Random Forest Regressor**, and **Gradient Boosting Regressor** — using `GridSearchCV` for optimal performance.
---

## 🗒️📌 Key Features Used

| Feature Name             | Description                                      |
|--------------------------|--------------------------------------------------|
| income                   | Annual income of the applicant                   |
| loan_amount              | Total amount of the requested loan               |
| loan_term                | Duration of the loan in months                   |
| interest_rate            | Interest rate applied to the loan                |
| debt_to_income_ratio     | Ratio of total debt to annual income             |
| employment_years         | Years employed at current job                    |
| savings_balance          | Current savings balance                          |
| age                      | Age of the applicant                             |

---

## 🧩⚙️ The Approach

### 1. Data Loading and Cleaning

- The dataset was loaded using `pandas`.
- Null values were checked using `.isnull().sum()` and handled appropriately (e.g., imputation or removal).
- Data types were verified and converted if necessary (e.g., converting categorical variables to numeric).
- Outliers were identified and treated using statistical methods like IQR or domain knowledge.
- 
### 2. Multicollinearity Handling: Successive VIF Testing
- A **Variance Inflation Factor (VIF)** test was performed to detect multicollinearity.
- Features with a VIF value greater than **10** were removed iteratively.
- After dropping the feature with high VIF (`credit_score`), a second VIF test confirmed all remaining features were within acceptable limits.

**Final VIF Results:**

| Feature                  | VIF Value |
|--------------------------|-----------|
| income                   | 5.49      |
| loan_amount              | 4.94      |
| loan_term                | 5.01      |
| interest_rate            | 5.62      |
| debt_to_income_ratio     | 6.47      |
| employment_years         | 3.40      |
| savings_balance          | 3.52      |
| age                      | 7.53      |

All features passed the VIF threshold (<10), indicating low multicollinearity.

---

### 3. Model Training & Selection

Three regression models were trained and tuned:

#### ✅ Ridge Regression
- Grid search over `alpha`: `[0.1, 1, 10, 100]`
- Optimized for minimum Mean Squared Error (MSE)

#### 🌲 Random Forest Regressor
- Hyperparameters: `n_estimators`, `max_depth`
- Searched over combinations: `[100, 200]`, `[None, 10, 20]`

#### 🚀 Gradient Boosting Regressor
- Parameters: `n_estimators`, `learning_rate`, `max_depth`
- Searched over: `[100, 200]`, `[0.01, 0.1]`, `[3, 5]`

---

### 4. Evaluation Metrics

Each model was evaluated using:
- **Mean Squared Error (MSE)**
- **Root Mean Squared Error (RMSE)**
- **R-squared (R²) Score**

The **best performing model** was selected based on these metrics.
- ✅ Ridge Regression
---

## 📁 File Structure

Default-risk-score-prediction/
│
├── data/ # Dataset files
│ └── data.csv # Main dataset
│
├── notebooks/ # Jupyter Notebooks for EDA and modeling
│ └── exploratory_analysis.ipynb
│
├── src/ # Source scripts
│ └── train_model.py # Script for training and evaluating models
│
├── README.md # This file
└── requirements.txt # Python dependencies
