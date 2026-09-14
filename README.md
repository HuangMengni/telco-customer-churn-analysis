# Telco Customer Churn Prediction

## Business Problem
A telecom company loses revenue when customers cancel subscriptions.  
This project predicts churn and identifies key drivers to support retention strategy.

## Data
- Source: Kaggle Telco Customer Churn
- 7,043 customers, 21 features
- Target: Churn (Yes/No), 26.5% positive rate

## Methods
- Python (Pandas, Scikit-learn, XGBoost, SHAP)
- 5-fold stratified cross-validation + grid search
- Models: Logistic Regression, Random Forest, XGBoost
- Class imbalance handled with class_weight / scale_pos_weight
- Evaluated by Accuracy, Precision, Recall, F1, AUC-ROC

## Key Findings
- Month-to-month contracts have the highest churn rate
- Short tenure + high monthly charges = high risk
- Lack of online security / tech support increases churn

## Model Performance
- XGBoost: Test AUC 0.840; Logistic Regression baseline: Test AUC 0.835
- 5-fold cross-validation confirmed XGBoost as the most robust model

## Cost-Sensitive Threshold Optimization
Because missing a churner (FN) is far more costly than false-alarming a loyal user (FP), we optimized the decision threshold.

- Assumed FN cost: $780 | Assumed FP cost: $50
- Optimal threshold: 0.05
- **Total cost reduced from $141,420 (default 0.5) to $38,240 (optimal threshold)**
- Cost reduction: over 70%

## Model Interpretation (SHAP)
SHAP summary plot identified the strongest churn drivers:
- Contract type (Two-year contracts strongly reduce churn)
- Tenure (short tenure = high risk)
- Fiber-optic internet service (associated with higher churn)
- Monthly charges

## Business Recommendations
1. Offer annual contract discounts to month-to-month users
2. Strengthen onboarding in the first 3 months (high-risk low-tenure group)
3. Bundle security/support services for fiber-optic users
4. Score customers weekly using the cost-optimized threshold (0.05) and alert the retention team

## Files
- `Telco_Churn_Analysis.ipynb`: Main analysis notebook
- `WA_Fn-UseC_-Telco-Customer-Churn.csv`: Dataset
