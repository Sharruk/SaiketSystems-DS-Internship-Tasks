# 🧪 Task-2 — Exploratory Data Analysis (EDA)

**Saiket Systems – Data Science Internship**

---

## 📌 Overview

This task performs a complete **Exploratory Data Analysis (EDA)** on the cleaned **Telco Customer Churn dataset**.

The goal is to explore customer behavior, detect churn patterns, and extract key business insights that will guide segmentation and prediction tasks in upcoming modules.

---

## 🎯 Objectives

- Understand customer demographics and churn rate
- Explore service usage patterns and contract behavior
- Analyze tenure, billing, and payment method trends
- Study correlations between features and churn
- Identify high-risk customer segments

This task builds the foundation for:

- 🔜 **Task-3 — Customer Segmentation**
- 🔜 **Task-4 — Churn Prediction Modeling**

---

## 📂 Folder Structure

```bash
Task-2_Exploratory_Data_Analysis/
│
├── README.md
├── notebook.ipynb
└── dataset/
    └── Telco_Customer_Churn_Dataset_cleaned.csv
```

📥 Dataset Used

Dataset: Telco_Customer_Churn_Dataset_cleaned.csv

Source: Output of Task-1 (Data Preparation)

Rows: 7,043

Columns: 32

Target Variable: Churn_Yes

The dataset contains no missing values and all categorical variables are encoded.


📊 EDA Summary
🔹 Churn Distribution

~26.5% of customers have churned

Dataset is moderately imbalanced (common in telecom)

🔹 Demographic Patterns

Customers without a partner or dependents show higher churn

Gender has minimal impact on churn behavior

🔹 Tenure Behavior

Churn is highest among customers with tenure < 12 months

Long-term customers (24+ months) are less likely to churn

🔹 Service Usage Insights

Fiber optic users churn more than DSL users

Lack of security or tech support services increases churn

🔹 Contract & Billing

Month-to-month customers are at highest risk

1-year and 2-year contracts reduce churn significantly

Electronic check users show much higher churn than others

🔹 Numerical Feature Insights

High monthly charges correlate with churn

Low total charges → recently acquired customers → more churn

🔹 Correlation Analysis

Top features correlated with churn:

Low tenure

Month-to-month contract

Electronic check

Fiber optic internet

No security/tech support add-ons

🚨 High-Risk Segments Identified
Segment Description	Churn Risk
Month-to-month + Electronic Check users	🔴 High
Fiber Optic + No Online Security	🔴 High
Tenure < 12 months	🔴 High
Senior citizens with no partner/dependents	🟠 Medium
High monthly charge customers	🟠 Medium
🧠 Key Takeaways

Tenure and contract type are the strongest churn predictors

Payment method and service support affect customer retention

EDA reveals actionable segments for targeted interventions

📦 Output

✔️ EDA Notebook: notebook.ipynb
✔️ Cleaned Dataset Used: dataset/Telco_Customer_Churn_Dataset_cleaned.csv
