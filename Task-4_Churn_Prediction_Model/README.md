📌 Task 4: Churn Prediction Model
🎯 Objective

The objective of this task is to build, evaluate, and compare machine learning models to predict customer churn in a telecommunications company.

Multiple classification algorithms are implemented and evaluated using appropriate performance metrics.
The best-performing model is selected for further interpretation and business recommendations.

📂 Dataset Used

Source: Cleaned dataset from Task 1 – Data Preparation

File Name: Telco_Customer_Churn_Dataset_cleaned.csv

The dataset includes:

Customer demographics

Service usage details

Contract and billing information

Churn labels

⚙️ Machine Learning Workflow

The churn prediction pipeline follows these steps:

Data loading and inspection

Feature–target separation

Stratified train–test split

Feature scaling (where applicable)

Model training and evaluation

Model comparison and final selection

🎯 Target Variable

Target Column: Churn_Yes

Problem Type: Binary Classification

Value	Meaning
1	Customer churned
0	Customer retained
🔀 Train–Test Split

Training Set: 80%

Testing Set: 20%

Sampling Strategy: Stratified

Stratification ensures the churn distribution remains consistent across training and testing datasets.

⚖️ Feature Scaling

Applied To: Logistic Regression

Scaler Used: StandardScaler

Tree-based models (Decision Tree and Random Forest) do not require feature scaling.

🤖 Models Implemented
1️⃣ Logistic Regression

Used as a baseline model

Simple and interpretable

Class imbalance handled using class_weight="balanced"

2️⃣ Decision Tree Classifier

Captures non-linear relationships

Rule-based learning approach

Balanced class weights applied

3️⃣ Random Forest Classifier

Ensemble of multiple decision trees

Reduces overfitting

Hyperparameter tuning performed using GridSearchCV

Optimized using F1-score

📊 Evaluation Metrics

Each model is evaluated using:

Accuracy

Precision

Recall

F1-score

🚨 Since churn data is imbalanced, F1-score is prioritized.

Additionally:

ROC-AUC is calculated for the Random Forest model to assess ranking performance.

📈 Model Performance Summary

| Model               | Accuracy  | Precision | Recall    | F1-Score  | ROC-AUC   |
| ------------------- | --------- | --------- | --------- | --------- | --------- |
| Logistic Regression | 0.740     | 0.506     | 0.786     | 0.616     | —         |
| Decision Tree       | 0.731     | 0.493     | 0.484     | 0.489     | —         |
| **Random Forest**   | **0.773** | **0.553** | **0.757** | **0.639** | **0.843** |


Note: ROC-AUC is reported only for Random Forest, as it provides reliable probability estimates.

✅ Final Model Selection

Among the evaluated models, Random Forest demonstrated the best overall performance:

Highest F1-score

Strong balance between precision and recall

High ROC-AUC score

➡️ Random Forest is selected as the final churn prediction model.

🧠 Key Takeaways

Ensemble models outperform individual classifiers for churn prediction

Handling class imbalance significantly improves recall

F1-score is more reliable than accuracy for churn-related problems

📌 Next Steps

The following analyses are covered in Task 5:

ROC curve analysis

Confusion matrix evaluation

Feature importance interpretation

Business-driven churn reduction recommendations

📁 Project Structure
```bash
Task-4_Churn_Prediction_Model/
│
├── README.md
└── notebook.ipynb
```

