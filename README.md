# Telco Customer Churn Analysis

## Business Problem
A telecom company loses revenue when customers cancel subscriptions. 
This project predicts churn and identifies key drivers to support retention strategy.

## Data
- Source: Kaggle Telco Customer Churn
- 7,043 customers, 21 features
- Target: Churn (Yes/No)

## Methods
- Python (Pandas, Scikit-learn, XGBoost)
- EDA → Data cleaning → Feature encoding → Train-test split
- Models: Logistic Regression, Random Forest, XGBoost
- Handled class imbalance (27% churn) with class_weight
- Evaluated by Accuracy, Precision, Recall, F1, AUC-ROC

## Key Findings
- Month-to-month contracts have highest churn rate
- Short tenure + high monthly charges = high risk
- Lack of online security/tech support increases churn

## Model Performance
- XGBoost: AUC [0.833], Recall [0.781], F1 [0.617]
- Selected for retention use case (catching churners matters more than false alarms)

## Business Recommendations
1. Offer annual contract discounts to month-to-month users
2. Strengthen onboarding in first 3 months
3. Bundle security/support services
4. Score customers weekly and alert retention team

## Files
- `Telco_Churn_Analysis.ipynb`: Main analysis notebook
