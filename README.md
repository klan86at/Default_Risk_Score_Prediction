# 📊 Credit Risk Score Prediction Project

## 🔍 Overview
This project aims to predict credit risk scores based on various financial and demographic features. The goal is to build a robust regression model that accurately estimates the creditworthiness of individuals, helping lenders make informed decisions.

Multicollinearity among features was addressed using the **Variance Inflation Factor (VIF)** test. Multiple regression models were evaluated — **Ridge Regression**, **Random Forest Regressor**, and **Gradient Boosting Regressor** — with hyperparameter tuning via `GridSearchCV`. The best-performing model was selected based on evaluation metrics such as **MSE**, **RMSE**, and **R² score**.

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

### 1. Multicollinearity Handling: Successive VIF Testing
- A **Variance Inflation Factor (VIF)** test was performed to detect multicollinearity.
- Features with a VIF value greater than **10** were removed iteratively.
- After dropping the feature with high VIF (e.g., `credit_score`), a second VIF test confirmed all remaining features were within acceptable limits.

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

### 2. Model Training & Selection

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

### 3. Evaluation Metrics

Each model was evaluated using:
- **Mean Squared Error (MSE)**
- **Root Mean Squared Error (RMSE)**
- **R-squared (R²) Score**

The **best performing model** was selected based on these metrics.

---

## 📁 File Structure
profile
Qwen3-235B-A22B
12:43 pm
Sure! Here's the full README.md content in a format ready to be saved as a .md file. You can copy and paste this into a new file named README.md in your project directory.

✅ Instructions to Save:
Open any text editor (e.g., VS Code, Notepad, Sublime Text).
Paste the content below.
Save the file as README.md.
markdown


1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
⌄
⌄
⌄
⌄
⌄
⌄
⌄
⌄
⌄
⌄
⌄
⌄
# 📊 Credit Risk Score Prediction Project

## 🔍 Overview
This project aims to predict credit risk scores based on various financial and demographic features. The goal is to build a robust regression model that accurately estimates the creditworthiness of individuals, helping lenders make informed decisions.

Multicollinearity among features was addressed using the **Variance Inflation Factor (VIF)** test. Multiple regression models were evaluated — **Ridge Regression**, **Random Forest Regressor**, and **Gradient Boosting Regressor** — with hyperparameter tuning via `GridSearchCV`. The best-performing model was selected based on evaluation metrics such as **MSE**, **RMSE**, and **R² score**.

---

## 🧠 Key Features Used

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

## ⚙️ Methodology

### 1. Multicollinearity Handling: Successive VIF Testing
- A **Variance Inflation Factor (VIF)** test was performed to detect multicollinearity.
- Features with a VIF value greater than **10** were removed iteratively.
- After dropping the feature with high VIF (e.g., `credit_score`), a second VIF test confirmed all remaining features were within acceptable limits.

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

### 2. Model Training & Selection

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

### 3. Evaluation Metrics

Each model was evaluated using:
- **Mean Squared Error (MSE)**
- **Root Mean Squared Error (RMSE)**
- **R-squared (R²) Score**

The **best performing model** was selected based on these metrics.

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
