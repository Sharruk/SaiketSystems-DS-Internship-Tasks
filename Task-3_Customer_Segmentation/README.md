# 🧩 Task-3 — Customer Segmentation

**Saiket Systems – Data Science Internship**

---

## 📌 Overview

This task focuses on **Customer Segmentation** using both **rule-based (business-friendly)** and **machine learning–based (KMeans)** approaches on the **Telco Customer Churn dataset**.

The goal is to segment customers based on **tenure**, **monthly charges**, and **contract type**, analyze churn behavior within each segment, and identify **high-value customers at risk of churning** for targeted business action.

This task acts as a bridge between:

* **Task-2 — Exploratory Data Analysis**
* **Task-4 — Churn Prediction Modeling**

---

## 🎯 Objectives

* Create **explainable customer segments** using business rules
* Analyze **churn rate, customer count, and revenue** per segment
* Identify **high-risk and high-value** customer groups
* Perform **KMeans clustering** as an alternative segmentation approach
* Generate a **priority retention list** for business teams

**Downstream Usage:**

* 🔜 Task-4 — Churn Prediction Model
* 🔜 Task-6 — Business Recommendations

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

---

## 📥 Datasets Used

### 🔹 Input Dataset

| Attribute           | Description                             |
| ------------------- | --------------------------------------- |
| **Source**          | Output of Task-1 & Task-2               |
| **Rows**            | 7,043                                   |
| **Columns**         | 32                                      |
| **Target Variable** | `Churn_Yes` (1 = Churned, 0 = Retained) |

---

### 🔹 Output Dataset

**Telco_Customer_Churn_Dataset_segmented.csv** contains:

* Rule-based segment labels
* KMeans cluster labels
* All original customer features

---

## 🧠 Segmentation Approaches

---

### 1️⃣ Rule-Based Segmentation (Explainable)

Customers are segmented using **three business-relevant dimensions**.

#### 🔸 Tenure Buckets

| Category    | Definition   |
| ----------- | ------------ |
| New         | ≤ 12 months  |
| Established | 13–36 months |
| Loyal       | > 36 months  |

#### 🔸 Monthly Charges Buckets

* Low
* Medium
* High *(based on terciles)*

#### 🔸 Contract Type

* Month-to-month
* One-year
* Two-year

**📌 Composite Segment Example:**
`New (≤12 months) | High Charges | Month-to-month`

This approach is **fully interpretable** and easily understood by **non-technical stakeholders**.

---

### 2️⃣ Segment-Level Churn & Revenue Analysis

For each rule-based segment, the following metrics were calculated:

* Customer count
* Churn count and churn rate
* Average monthly charges
* Average total charges
* Estimated monthly revenue

**📁 Output File:**
`reports/segment_summary_rulebased.csv`

---

### 3️⃣ Risk Categorization

Segments were classified into **four business risk categories**:

| Risk Category           | Description                      |
| ----------------------- | -------------------------------- |
| 🔴 High-Risk High-Value | High churn & high revenue impact |
| 🔴 High-Risk Low-Value  | High churn, lower revenue        |
| 🟢 Low-Risk High-Value  | Stable but valuable customers    |
| ⚪ Normal                | Average risk and value           |

**Criteria Applied:**

* Top 30% churn rate
* Top 30% average monthly charges
* Minimum segment size threshold

📌 Thresholds were chosen to balance **business actionability** and **statistical reliability**.

---

### 4️⃣ KMeans Clustering (Algorithmic Segmentation)

An alternative **data-driven segmentation** was performed using **KMeans clustering**.

**Features Used:**

* Tenure
* MonthlyCharges
* TotalCharges
* InternetService (Fiber optic)
* PaymentMethod (Electronic check)

**Process Followed:**

* Feature scaling using `StandardScaler`
* KMeans evaluated for **k = 2 to 6**
* Optimal k selected using **Silhouette Score**
* PCA applied for 2D cluster visualization

**📁 Output File:**
`reports/segment_summary_kmeans.csv`

---

## 🚨 High-Value & At-Risk Customers

Customers were flagged as **high-value & at-risk** if they:

* Belong to **high-risk rule-based segments**, or
* Fall into **high-churn KMeans clusters**, and
* Are in the **top quartile** of MonthlyCharges or TotalCharges

**📁 Priority Retention Dataset:**
`reports/high_value_at_risk_customers.csv`

**Intended Business Use:**

* Retention campaigns
* Personalized offers
* Proactive customer outreach

---

## 📊 Key Insights

* Month-to-month customers with **high charges** show the highest churn risk
* **New customers (≤12 months)** are extremely churn-prone
* **Two-year contracts** significantly reduce churn
* **Electronic check** payment method strongly correlates with churn
* Rule-based and KMeans approaches reveal **consistent churn patterns**

---

## 📦 Outputs Summary

| File Name                                  | Description                           |
| ------------------------------------------ | ------------------------------------- |
| Telco_Customer_Churn_Dataset_segmented.csv | Dataset with segment & cluster labels |
| segment_summary_rulebased.csv              | Rule-based segment metrics            |
| segment_summary_kmeans.csv                 | KMeans cluster summary                |
| high_value_at_risk_customers.csv           | Priority retention customer list      |

---

## 🧠 Business Relevance

* Enables **targeted retention strategies**
* Supports **contract upgrade and pricing incentives**
* Helps prioritize **high-revenue churn risks**
* Provides **explainable insights** for non-technical stakeholders

---
