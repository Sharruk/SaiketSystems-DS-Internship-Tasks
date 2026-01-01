# 📊 Task 4: Churn Prediction Model

## 🎯 Objective

The objective of this task is to build and evaluate **machine learning classification models**
to predict customer churn in a telecommunications company.

Multiple classification algorithms are implemented and compared using appropriate
evaluation metrics. The **best-performing model** is selected for further analysis,
while accounting for the  **imbalanced nature of churn data** .

---

## 📂 Dataset Used

* **Source:** Cleaned dataset from **Task-1 – Data Preparation**
* **File Name:** `Telco_Customer_Churn_Dataset_cleaned.csv`

The dataset includes:

* Customer demographics
* Service usage information
* Contract and billing details
* Churn labels

---

## 🧩 Feature–Target Definition

* **Target Variable:** `Churn_Yes`
  * `1` → Customer churned
  * `0` → Customer retained
* **Features:**
  All remaining columns except `customerID` and `Churn_Yes`

---

## 🔀 Train–Test Split

The dataset is split using **stratified sampling** to preserve the original churn
distribution.

* **Training Set:** 80%
* **Testing Set:** 20%
* **Random State:** 42

---

## ⚖️ Feature Scaling

* **StandardScaler** is applied **only to Logistic Regression**
* Tree-based models ( **Decision Tree, Random Forest** ) do not require feature scaling

---

## 📊 Model Evaluation Strategy

Models are evaluated using the following metrics:

* Accuracy
* Precision
* Recall
* F1-Score
* ROC-AUC

⚠️ Since churn data is  **imbalanced** ,  **Recall** ,  **F1-Score** , and **ROC-AUC**
are prioritized over accuracy to reduce false negatives (missed churners).

---

## 🤖 Models Implemented

### 1️⃣ Logistic Regression

* Used as a baseline model
* Simple and interpretable
* Class imbalance handled using `class_weight="balanced"`
* Feature scaling applied

---

### 2️⃣ Decision Tree Classifier

* Rule-based model
* Captures non-linear relationships
* Balanced class weights applied
* No feature scaling required

---

### 3️⃣ Random Forest Classifier

* Ensemble of multiple decision trees
* Reduces overfitting
* Hyperparameter tuning performed using **GridSearchCV**
* Optimized using **F1-Score**
* Balanced class weights applied

---

## 📈 Model Performance Comparison

All trained models are compared below. Metric values are rounded for clarity.

| Model                   | Accuracy        | Precision       | Recall          | F1-Score        | ROC-AUC         |
| ----------------------- | --------------- | --------------- | --------------- | --------------- | --------------- |
| Logistic Regression     | 0.740           | 0.506           | 0.786           | 0.616           | 0.841           |
| Decision Tree           | 0.731           | 0.493           | 0.484           | 0.489           | 0.653           |
| **Random Forest** | **0.773** | **0.553** | **0.757** | **0.639** | **0.843** |

**Note:**
Accuracy alone is insufficient for churn prediction.
 **Recall** ,  **F1-Score** , and **ROC-AUC** are emphasized due to class imbalance.

---

## ✅ Final Model Selection

Among all evaluated models, **Random Forest** achieved the best overall performance.

### Reasons for selection:

* Highest  **F1-Score** , indicating a strong balance between precision and recall
* Strong  **ROC-AUC** , showing superior discrimination ability
* Effectively captures non-linear feature interactions
* Robust performance on imbalanced churn data

➡️ **Random Forest is selected as the final churn prediction model.**

---

## 🔍 Feature Importance Analysis

Feature importance scores are extracted from the trained Random Forest model to
identify the key drivers of customer churn.

### 🔝 Top Influential Features

* **Tenure** – New customers are more likely to churn
* **TotalCharges** – Indicates customer lifetime value
* **MonthlyCharges** – Higher charges increase churn risk
* **Contract Type (One-Year / Two-Year)** – Long-term contracts reduce churn
* **Payment Method (Electronic Check)** – Strongly associated with churn

⚠️ Feature importance reflects  **relative influence** , not causation, and should
be interpreted alongside EDA and business context.

---

## 💾 Model Persistence

The best-performing Random Forest model selected using **GridSearchCV**
is saved to disk for reuse in subsequent tasks.

### Benefits of saving the model:

* Ensures reproducibility
* Avoids retraining in later tasks
* Enables clean, production-style workflows

**Saved Model File:**

* `best_random_forest_model.pkl`

This model will be loaded directly in  **Task-5 – Model Evaluation and Interpretation** .

---

## 🧠 Conclusion

This task successfully implemented and evaluated multiple machine learning models
for customer churn prediction.

Among them, **Random Forest** demonstrated the best overall performance and was
selected as the final model. Its strong predictive power, robustness, and
interpretability make it suitable for real-world customer retention strategies.

Further business insights and model interpretation are covered in  **Task-5** .

---

## 📁 Project Structure

```bash
Task-4_Churn_Prediction_Model/
│
├── README.md
├── notebook.ipynb
└── best_random_forest_model.pkl
```

---

## ✅ FINAL QUALITY CHECK

✔ Fully aligned with notebook
✔ ROC-AUC included correctly
✔ No redundancy
✔ Internship & recruiter ready
✔ Production-style workflow

If you want next:

* 🔥 Task-5 README (same polish)
* 📄 One **master README** for entire project
* 🧾 Resume bullet points from this project

Just tell me 👍

