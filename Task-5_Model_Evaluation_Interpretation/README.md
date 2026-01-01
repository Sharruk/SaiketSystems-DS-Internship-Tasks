# 📌 Task 5: Model Evaluation and Interpretation

**Saiket Systems – Data Science Internship**

---

## 🎯 Objective

The objective of this task is to **evaluate the final churn prediction model**
using the testing dataset and **interpret the key factors influencing customer churn**.

This task focuses on:

- Evaluating model performance using classification metrics  
- Analyzing ROC curve and AUC score  
- Interpreting feature importance to understand churn drivers  

---

## 📂 Dataset Used

- **Source:** Cleaned dataset from **Task 1 – Data Preparation**
- **File Name:** `Telco_Customer_Churn_Dataset_cleaned.csv`

The dataset contains customer demographics, service details, billing information,
and churn labels.

---

## ⚙️ Model Used

Based on **Task 4 – Model Comparison**, the **Random Forest Classifier** was selected
as the final model due to its superior overall performance.

### Model Configuration

- Number of trees: 200  
- Class imbalance handled using `class_weight="balanced"`  
- Random state set for reproducibility  

---

## 🔀 Train–Test Strategy

- **Training Set:** 80%  
- **Testing Set:** 20%  
- **Sampling Method:** Stratified  

Stratification ensures the churn distribution remains consistent across splits.

---

## 📊 Model Evaluation Metrics

The model is evaluated on the test dataset using:

- Accuracy  
- Precision  
- Recall  
- F1-score  
- ROC-AUC  

Since churn prediction is an imbalanced classification problem, **F1-score and ROC-AUC**
are emphasized over accuracy.

---

## 📈 Model Performance Results

| Metric     | Score |
|-----------|-------|
| Accuracy  | 0.794 |
| Precision | 0.645 |
| Recall    | 0.500 |
| F1-Score  | 0.563 |
| ROC-AUC   | 0.826 |

---

## 🔍 Confusion Matrix Analysis

The confusion matrix provides insight into:

- Correct predictions  
- False positives  
- False negatives  

False negatives are particularly critical, as failing to identify a churn-prone
customer may result in revenue loss.

The confusion matrix visualization helps assess the balance between churn detection
and incorrect churn predictions.

---

## 📉 ROC Curve Analysis

The ROC curve illustrates the model’s ability to distinguish between churned and
non-churned customers across various threshold values.

- A higher AUC score indicates better ranking performance  
- The model achieves a **strong ROC-AUC of 0.826**, indicating good separation capability  

---

## 🧠 Feature Importance Analysis

Random Forest provides feature importance scores that highlight the most influential
factors contributing to customer churn.

### 🔝 Top Influential Features

| Feature | Importance |
|-------|------------|
| TotalCharges | High |
| tenure | High |
| MonthlyCharges | High |
| Contract_Two year | Moderate |
| InternetService_Fiber optic | Moderate |
| PaymentMethod_Electronic check | Moderate |
| Contract_One year | Moderate |
| OnlineSecurity_Yes | Moderate |
| gender_Male | Low |
| PaperlessBilling_Yes | Low |

---

## 📊 Feature Importance Visualization

The top 10 features are visualized to provide a clear understanding of their
relative contribution to churn prediction.

This visualization helps bridge the gap between **model performance** and
**business interpretation**.

---

## 🧠 Final Interpretation and Business Insights

The analysis reveals several important churn drivers:

- Customers on **short-term contracts** are more likely to churn  
- **Low-tenure customers** exhibit higher churn risk  
- **Higher monthly charges** increase churn probability  
- **Payment method** plays a significant role in customer retention  
- Internet and streaming services influence churn behavior  

---

## 📌 Business Recommendations

Based on model interpretation:

- Introduce incentives for long-term contracts  
- Target new customers with retention-focused onboarding programs  
- Optimize pricing strategies for high monthly charge customers  
- Encourage stable payment methods  
- Improve service bundling for internet and streaming services  

---

## 🏁 Task 5 Completion Summary

✔ Final model evaluated on test data  
✔ Confusion matrix analyzed  
✔ ROC curve and AUC evaluated  
✔ Feature importance interpreted  
✔ Actionable business insights extracted  

---

## 📁 Project Structure

```bash
Task-5_Model_Evaluation_and_Interpretation/
│
├── README.md
└── notebook.ipynb
