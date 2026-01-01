# 📊 Task 5: Model Evaluation and Interpretation

## 🎯 Objective

The objective of this task is to **evaluate and interpret the final churn prediction model**
selected in  **Task-4** .

The **best-performing Random Forest model** is evaluated on unseen test data to assess
its real-world performance and extract **business-relevant insights** that explain
customer churn behavior.

To ensure  **consistency and reproducibility** , the model trained and saved in Task-4
is loaded directly without retraining.

---

## 📂 Dataset Used

* **Source:** Cleaned dataset from **Task-1 – Data Preparation**
* **File Name:** `Telco_Customer_Churn_Dataset_cleaned.csv`

The dataset contains:

* Customer demographics
* Service usage details
* Contract and billing information
* Churn labels

---

## 🧩 Feature–Target Definition

* **Target Variable:** `Churn_Yes`
  * `1` → Customer churned
  * `0` → Customer retained
* **Features:**
  All columns except `customerID` and `Churn_Yes`

---

## 🔀 Train–Test Split

The dataset is split using **stratified sampling** to preserve the original churn
distribution.

* **Training Set:** 80%
* **Testing Set:** 20%
* **Random State:** 42

---

## 🤖 Final Model Used

* **Model:** Random Forest Classifier
* **Source:** Loaded from **Task-4**
* **File:** `best_random_forest_model.pkl`

### Why reuse the saved model?

* Ensures consistent performance metrics
* Avoids retraining bias
* Reflects real-world deployment scenarios

---

## 📊 Model Performance Evaluation

The final model is evaluated using the following classification metrics:

* Accuracy
* Precision
* Recall
* F1-Score
* ROC-AUC

### 📈 Evaluation Results

| Metric    | Value |
| --------- | ----- |
| Accuracy  | 0.773 |
| Precision | 0.553 |
| Recall    | 0.757 |
| F1-Score  | 0.639 |
| ROC-AUC   | 0.843 |

⚠️ Since churn data is  **imbalanced** ,  **Recall** ,  **F1-Score** , and **ROC-AUC**
are prioritized to reduce missed churners.

---

## 📉 Confusion Matrix Analysis

The confusion matrix provides a detailed breakdown of correct and incorrect predictions.

* **True Positives:** Correctly identified churners
* **False Negatives:** Churners predicted as non-churners (high business cost)

Minimizing false negatives is crucial, as they represent customers who may leave
without preventive retention actions.

---

## 📈 ROC Curve and AUC Analysis

The ROC curve illustrates the model’s ability to distinguish between churned and
non-churned customers across different classification thresholds.

* **AUC Score:** 0.84
* Indicates strong discriminatory power
* Confirms stable and reliable ranking performance

---

## 🔍 Feature Importance Analysis

Random Forest feature importance is used to interpret the factors that most influence
customer churn.

### 🔝 Top Influential Features

* **Tenure** – New customers are more likely to churn
* **TotalCharges** – Reflects customer lifetime value
* **MonthlyCharges** – Higher charges increase churn risk
* **Contract Type (Two-Year / One-Year)** – Long-term contracts reduce churn
* **Payment Method (Electronic Check)** – Strongly associated with churn
* **Internet & Support Services** – Service quality impacts retention

⚠️ Feature importance represents  **relative influence** , not causation, and should
be interpreted alongside EDA and business understanding.

---

## 📊 Feature Importance Visualization

The top 10 most influential features are visualized using a horizontal bar chart to
clearly highlight the strongest churn drivers.

This visualization helps translate model outputs into  **actionable business insights** .

---

## 🧠 Business Insights & Recommendations

Based on the model interpretation:

* Offer incentives to **new customers** during early tenure
* Encourage **long-term contracts** to reduce churn risk
* Review pricing strategies for customers with **high monthly charges**
* Promote alternative **payment methods** over electronic checks
* Improve **internet and support service quality**

These insights can directly support customer retention strategies and decision-making.

---

## 🏁 Conclusion

This task successfully evaluated and interpreted the final churn prediction model
selected in Task-4.

The **Random Forest model** demonstrates:

* Strong predictive performance
* High discrimination ability (ROC-AUC > 0.8)
* Clear interpretability through feature importance

The model is **ready for deployment** and provides meaningful insights to guide
business-level churn reduction strategies.

---

## 📁 Project Structure

```bash
Task-5_Model_Evaluation_and_Interpretation/
│
├── README.md
└── notebook.ipynb
```

---
