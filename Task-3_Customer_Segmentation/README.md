# 🧩 Task-3 — Customer Segmentation

**Saiket Systems – Data Science Internship**

---

## 📌 Overview

This task focuses on **Customer Segmentation** using both **rule-based (business-friendly)** and **machine learning–based (KMeans)** approaches on the Telco Customer Churn dataset.

The objective is to segment customers based on tenure, monthly charges, and contract type, analyze churn behavior within segments, and identify **high-value customers who are at risk of churning** for targeted business action.

This task bridges insights from **Exploratory Data Analysis (Task-2)** and **predictive modeling (Task-4)**.

---

## 🎯 Objectives

- Create explainable customer segments using business rules  
- Analyze churn rate, customer count, and revenue per segment  
- Identify high-risk and high-value customer segments  
- Perform KMeans clustering as an alternative segmentation approach  
- Extract a priority retention list for business teams  

This task supports:

- 🔜 **Task-4 — Churn Prediction Model**
- 🔜 **Task-6 — Business Recommendations**

---

## 📂 Folder Structure

```bash
Task-3_Customer_Segmentation/
│
├── README.md
├── notebook.ipynb
│
├── dataset/
│   ├── Telco_Customer_Churn_Dataset_cleaned.csv
│   └── Telco_Customer_Churn_Dataset_segmented.csv
│
└── reports/
    ├── segment_summary_rulebased.csv
    ├── segment_summary_kmeans.csv
    └── high_value_at_risk_customers.csv
```

📥 Datasets Used
🔹 Input Dataset

File: Telco_Customer_Churn_Dataset_cleaned.csv

Source: Output of Task-1 & Task-2

Rows: 7,043

Columns: 32

Target Variable: Churn_Yes (1 = Churned, 0 = Retained)

🔹 Output Dataset

File: Telco_Customer_Churn_Dataset_segmented.csv

Contains:

Rule-based segment labels

KMeans cluster labels

All original features

🧠 Segmentation Approaches
1️⃣ Rule-Based Segmentation (Explainable)

Customers are segmented using three business-relevant dimensions:

🔸 Tenure Buckets

New: ≤ 12 months

Established: 13–36 months

Loyal: > 36 months

🔸 Monthly Charges Buckets

Low

Medium

High (based on terciles)

🔸 Contract Type

Month-to-month

One-year

Two-year

Composite Segment Example:
New (≤12 months) | High Charges | Month-to-month

This approach ensures full interpretability and can be directly understood by non-technical stakeholders.

2️⃣ Segment-Level Churn & Revenue Analysis

For each rule-based segment, the following metrics were computed:

Number of customers

Churn count and churn rate

Average monthly charges

Average total charges

Estimated monthly revenue

📁 Output:
reports/segment_summary_rulebased.csv

3️⃣ Risk Categorization

Segments were categorized into:

🔴 High-Risk High-Value

🔴 High-Risk Low-Value

🟢 Low-Risk High-Value

⚪ Normal

Criteria Used:

Top 30% of churn rate

Top 30% of average monthly charges

Minimum segment size threshold applied

📌 Thresholds were chosen to balance business actionability and statistical significance.

4️⃣ KMeans Clustering (Algorithmic Segmentation)

An alternative, algorithm-driven segmentation was performed using KMeans clustering.

Features Used:

Tenure

MonthlyCharges

TotalCharges

InternetService_Fiber optic

PaymentMethod_Electronic check

Steps Followed:

Feature scaling using StandardScaler

KMeans evaluated for k = 2 to 6

Best k selected using Silhouette Score

PCA used for 2D cluster visualization

📁 Output:
reports/segment_summary_kmeans.csv

🚨 High-Value & At-Risk Customers

Customers were flagged as high-value & at-risk if they:

Belong to high-risk rule-based segments, or

Are part of high-churn KMeans clusters, and

Fall within the top quartile of MonthlyCharges or TotalCharges

📁 Priority Retention List:
reports/high_value_at_risk_customers.csv

This dataset is intended for:

Retention campaigns

Personalized offers

Proactive customer outreach

📊 Key Insights

Month-to-month customers with high charges show the highest churn risk

New customers (≤ 12 months) are extremely churn-prone

Two-year contracts significantly reduce churn

Electronic check payment method strongly correlates with churn

Rule-based and KMeans segments reveal consistent churn patterns

📦 Outputs Summary
File Name	Description
Telco_Customer_Churn_Dataset_segmented.csv	Dataset with segment & cluster labels
segment_summary_rulebased.csv	Rule-based segment metrics
segment_summary_kmeans.csv	KMeans cluster summary
high_value_at_risk_customers.csv	Priority retention customer list
🧠 Business Relevance

Enables targeted retention strategies

Supports contract upgrade and pricing incentives

Helps prioritize high-revenue churn risks

Provides explainable insights for non-technical stakeholders

✅ Status

✔ Task-3 completed successfully
✔ Ready for predictive modeling (Task-4)
✔ Directly usable for business recommendations (Task-6)
    ├── segment_summary_kmeans.csv
    └── high_value_at_risk_customers.csv
