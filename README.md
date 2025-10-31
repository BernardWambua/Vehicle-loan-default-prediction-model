# Vehicle Loan Default Prediction Model

## Overview

This project develops a **machine learning model** to predict the likelihood of a borrower defaulting on a vehicle loan.
Unlike traditional credit scoring systems that rely heavily on credit bureau data, this model also incorporates **alternative data sources** to evaluate **borrowers with limited or no credit history**.
The goal is to improve credit inclusion while maintaining robust risk control for financial institutions.

---

## Objectives

* Predict the probability of **vehicle loan default** based on both credit and non-credit features.
* Identify and assess **new-to-credit** applicants who may not be accurately graded by traditional credit ratings.
* Enhance **risk-based pricing**, **underwriting decisions**, and **portfolio management**.
* Ensure the model is **interpretable** and aligned with regulatory expectations.

---

## Model Summary

| Aspect                   | Description                                                  |
| ------------------------ | ------------------------------------------------------------ |
| **Problem Type**         | Binary Classification (`Default` vs `Non-default`)           |
| **Algorithms Tested**    | Logistic Regression, Random Forest, XGBoost, LightGBM        |
| **Final Model**          | Decision Tree-balance between accuracy and interpretability) |
| **Evaluation Metrics**   | AUC-ROC, Precision, Recall, F1-Score, KS Statistic           |
| **Explainability Tools** | SHAP values for global and local feature interpretation      |

---

## Data Description

The model combines **traditional credit data** with **alternative borrower attributes** to ensure fair assessment for all customers.

| Feature Group                                              | Examples                                                                            |
| ---------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| **Credit Bureau Data**                                     | Credit Score, Number of Open Accounts, Delinquency History                          |
| **Applicant Information**                                  | Age, Income, Employment Type, Education Level                                       |
| **Loan Details**                                           | Loan Amount, Tenure, Interest Rate, Vehicle Type                                    |
| **Behavioral Features**                                    | Payment Timeliness, Previous Loan Applications, Account Age                         |
| **Alternative Indicators (for thin/no-credit applicants)** | Utility bill payment patterns, mobile phone usage consistency, employment stability |
| **Derived Features**                                       | Debt-to-Income Ratio, Credit Utilization, Payment-to-Income Ratio                   |

* **Target Variable:** `loan_default` (1 = Default, 0 = Non-default)
* **Data Split:** 70% Training, 15% Validation, 15% Test

---

## Model Pipeline

1. **Data Preprocessing:** Handle missing data, encode categorical features, normalize continuous features
2. **Feature Engineering:** Combine credit and alternative attributes
3. **Model Training:** Hyperparameter tuning using stratified cross-validation
4. **Evaluation:** Use business-relevant thresholds for optimal precision-recall balance
5. **Explainability:** SHAP and permutation importance for transparency and trust
