# Customer Delinquency Prediction Using Machine Learning

## Project Overview
This project builds a **machine learning model to predict customer delinquency** based on financial behavior and demographic data. The goal is to help financial institutions **identify high-risk customers early** and take preventive action.

The project covers the **entire ML pipeline**:
- Data loading & cleaning
- Feature engineering
- Handling class imbalance
- Model training & evaluation
- Model interpretation & persistence

---

## Tech Stack & Tools
- **Python**
- **Jupyter Notebook / Google Colab**
- **pandas, numpy**
- **scikit-learn**
- **imbalanced-learn (SMOTE)**
- **XGBoost**
- **matplotlib, seaborn**
- **joblib**

---

## Dataset
- Source: `projectsampledata.xlsx`
- Target Variable: **Delinquent_Account**
- Features include:
  - Income
  - Credit Score
  - Loan Balance
  - Employment Status
  - Credit Card Type
  - Location
  - Monthly payment behavior

---

## Data Processing & Feature Engineering
- Handled missing values using **median imputation**
- Removed non-informative identifiers (Customer_ID)
- Applied **one-hot encoding** for categorical features
- Created a new behavioral feature:
  - **Missed_Late_Count** – counts missed or late payments across 6 months
- Addressed class imbalance using **SMOTE**

---

## Models Trained
- Logistic Regression
- Random Forest
- XGBoost (Best Performer)

---

## Model Evaluation
Evaluation metrics:
- Accuracy
- Confusion Matrix
- Precision, Recall, F1-score
- ROC Curve & AUC Score

**Best Model:** XGBoost  
- Accuracy: ~83%
- Strong performance on minority (delinquent) class

---

## Feature Importance
Top risk drivers identified:
- Missed_Late_Count
- Credit Score
- Employment Status
- Loan Balance

These insights provide **business interpretability** and actionable intelligence.

---

##  Model Saving
The final XGBoost model is saved for deployment using:
```python
joblib.dump(xgb_model, 'delinquency_model.pkl')
