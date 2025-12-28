# 🧹 Task 1 — Data Preparation

**Saiket Systems – Data Science Internship**

## 📌 Overview

This task focuses on preparing the **Telco Customer Churn dataset** for further analysis and machine learning tasks.

A clean and well-structured dataset is critical for accurate insights, reliable modeling, and meaningful business conclusions.

This notebook performs  **end-to-end data cleaning and preprocessing** , transforming raw data into a model-ready format.

---

## 🎯 Objective

To clean, preprocess, and encode the Telco Customer Churn dataset by:

* Handling missing values
* Fixing incorrect data types
* Treating outliers
* Cleaning categorical variables
* Encoding features for machine learning
* Exporting a finalized clean dataset

---

## 📂 Folder Structure
```bash
Task-1_Data_Preparation/
│
├── README.md
├── notebook.ipynb
└── dataset/
    ├── Telco_Customer_Churn_Dataset.csv
    └── Telco_Customer_Churn_Dataset_cleaned.csv
```
---

## 📥 Dataset Description

**Raw Dataset:** `Telco_Customer_Churn_Dataset.csv`

* Rows: 7,043
* Columns: 21
* Target Variable: `Churn`

**Cleaned Dataset:** `Telco_Customer_Churn_Dataset_cleaned.csv`

* Rows: 7,043
* Columns: 32 (after encoding)
* Missing Values: 0

---

## 🛠️ Steps Performed

### 1️⃣ Data Loading & Inspection

* Loaded raw CSV file
* Inspected shape, data types, and sample records
* Replaced blank spaces with `NaN`

---

### 2️⃣ Missing Value Analysis

* Identified missing values using summary statistics and heatmap
* Found missing values only in `TotalCharges` (11 rows)

---

### 3️⃣ Data Type Fixing

* Converted `TotalCharges` from `object` to numeric
* Imputed missing values using **median**

---

### 4️⃣ Text Normalization

* Removed leading/trailing spaces from categorical values
* Ensured consistency for encoding

---

### 5️⃣ Duplicate Removal

* Checked for duplicate records
* No duplicates found

---

### 6️⃣ Outlier Detection & Treatment

* Visualized outliers using boxplots and histograms
* Applied **1st–99th percentile capping** on:
  * `tenure`
  * `MonthlyCharges`
  * `TotalCharges`

---

### 7️⃣ Class Balance Check

* Verified churn class distribution
* Dataset shows moderate imbalance (acceptable for modeling)

---

### 8️⃣ Feature Encoding

* Applied **One-Hot Encoding** to categorical variables
* Excluded `customerID` from encoding
* Final feature count increased from **21 → 32**

---

### 9️⃣ Before vs After Validation

* Compared numeric distributions before and after preprocessing
* Ensured no distortion of data patterns

---

### 🔟 Final Validation & Export

* Confirmed **zero missing values**
* Saved cleaned dataset for downstream tasks

---

## 📊 Cleaning Summary

| Metric                 | Value                                        |
| ---------------------- | -------------------------------------------- |
| Initial Rows           | 7,043                                        |
| Final Rows             | 7,043                                        |
| Initial Columns        | 21                                           |
| Final Columns          | 32                                           |
| Duplicates Removed     | 0                                            |
| Missing Values (Final) | 0                                            |
| Outlier Handling       | 1st–99th percentile capping                 |
| Output File            | `Telco_Customer_Churn_Dataset_cleaned.csv` |

---

🧠 Key Outcome

The dataset is now fully cleaned, encoded, and validated, ensuring
high-quality input for exploratory analysis, segmentation, and
predictive modeling in subsequent tasks.


## 📦 Output

✔️ **Cleaned Dataset:**

`dataset/Telco_Customer_Churn_Dataset_cleaned.csv`

This dataset is used in:

* **Task 2:** Exploratory Data Analysis
* **Task 3:** Customer Segmentation
* **Task 4:** Churn Prediction Modeling

---


