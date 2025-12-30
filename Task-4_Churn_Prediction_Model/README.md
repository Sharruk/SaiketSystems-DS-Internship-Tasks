📌 Task 4: Churn Prediction Model
🎯 Objective

The objective of this task is to build and evaluate machine learning models to predict customer churn in a telecommunications company.

Multiple classification algorithms are implemented and compared using appropriate evaluation metrics. The best-performing model is then selected for further evaluation, interpretation, and business recommendations.

📂 Dataset Used

Source: Cleaned dataset from Task 1

File: Telco_Customer_Churn_Dataset_cleaned.csv

The dataset contains customer demographic details, service usage information, contract details, and churn labels.

⚙️ Machine Learning Workflow

The churn prediction pipeline follows these key steps:

Data loading and inspection

Feature–target separation

Train–test split using stratified sampling

Feature scaling (where applicable)

Model training and evaluation

Model comparison and selection

🎯 Target Variable

Target: Churn_Yes

Type: Binary classification

1 → Customer churned

0 → Customer retained

🔀 Train–Test Split

Training set: 80%

Testing set: 20%

Stratification: Applied to preserve churn distribution

This ensures fair evaluation and prevents class imbalance bias.

⚖️ Feature Scaling

Feature scaling is applied only to Logistic Regression using StandardScaler, as it is sensitive to feature magnitudes.

Tree-based models (Decision Tree and Random Forest) do not require scaling.

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

Ensemble of decision trees

Reduces overfitting

Hyperparameter tuning performed using GridSearchCV

Optimized using F1-score

📊 Evaluation Metrics

Each model is evaluated using:

Accuracy

Precision

Recall

F1-score

Due to class imbalance in churn data, F1-score is prioritized.

Additionally, ROC-AUC is calculated for the Random Forest model to assess its ranking ability.

📈 Model Performance Summary
Model	Accuracy	Precision	Recall	F1-Score	ROC-AUC
Logistic Regression	0.740	0.506	0.786	0.616	—
Decision Tree	0.731	0.493	0.484	0.489	—
Random Forest	0.773	0.553	0.757	0.639	0.843

Note: ROC-AUC is reported only for Random Forest, as it provides reliable probability estimates.

✅ Final Model Selection

Among the evaluated models, Random Forest demonstrated the best overall performance:

Highest F1-score

Strong balance between precision and recall

High ROC-AUC score

Therefore, Random Forest was selected as the final churn prediction model.

🧠 Key Takeaways

Ensemble methods outperform individual classifiers for churn prediction

Handling class imbalance significantly improves recall

F1-score is a more reliable metric than accuracy for churn problems

📌 Next Steps

Detailed evaluation and interpretation of the final model

ROC curve analysis and confusion matrix

Feature importance analysis

Business-driven churn reduction recommendations

These steps are addressed in Task 5: Model Evaluation and Interpretation.

📁 Files in This Directory
Task-4_Churn_Prediction_Model/
│
├── README.md
└── notebook.ipynb
