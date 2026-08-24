# Loan Eligibility Preprocessing and Feature Evaluation

Author: Ayden Demanou, Junior Data Scientist, AnalystLab Africa Consulting
Client Domain: Retail Financial Services
Project Goal: Build a robust, explainable data foundation for loan approval prediction
Dataset Source: Kaggle Loan Prediction Problem Dataset

## Project Overview

This repository contains the end-to-end analytics pipeline used across Week 2 and later phases:
1. Data cleaning and imputation.
2. Feature engineering guided by domain logic.
3. Advanced EDA and hypothesis testing.
4. Feature evaluation and selection using correlation and mutual information.
5. Refinement of the final modelling dataset for Week 4.

The outcome is a refined, modelling-ready dataset with reduced redundancy and stronger business interpretability.

## Current Repository Structure

```text
Loan Eligibility Preprocessing/
├── README.md
├── requirement.txt
├── charts/
├── data/
│   ├── train_u6lujuX_CVtuZ9i.csv
│   ├── test_Y3wMUE5_7gLdaTN.csv
│   └── processed/
│       ├── loan_prediction_cleaned.csv
│       ├── loan_prediction_feature_engineered.csv
│       ├── loan_prediction_ml_ready.csv
│       ├── loan_prediction_refined_cleaned.csv
│       ├── loan_prediction_refined_ml_ready.csv
│       └── final_modelling_dataset.csv
├── notebooks/
│   ├── loan_approval_prediction.ipynb
│   ├── advanced_eda_analysis_and_fe.ipynb
│   └── feature_selection_evaluation.ipynb
└── reports/
    ├── Business Understanding Report Loan Eligibility Prediction.pdf
    ├── Data Preprocessing Report.pdf
    ├── Business_Insights_and_Recommendations_Report.pdf
    └── Updated_Data_Dictionary.md
```

## Workflow Summary

### Week 2 Foundation
- Cleaned missing values and standardized categories.
- Built baseline engineered variables such as Total_Income and Loan_Income_Ratio.
- Produced cleaned and ML-ready datasets.

### Advanced Analysis
- Performed advanced exploratory analysis and statistical tests.
- Assessed variable behavior, significance, and interaction patterns.
- Identified strong structural effects such as concentrated 360-month loan terms.

### Feature Evaluation and Selection
- Evaluated redundancy and multicollinearity using correlation analysis.
- Ranked feature utility with mutual information.
- Removed low-value or redundant features and retained interpretable predictors.

### Dataset Refinement
- Added Is_Standard_Term as a high-value engineered feature.
- Applied RobustScaler to:
	- Loan_Amount_Term
	- Income_to_LoanTerm_Interaction
- Produced final Week 4 modelling dataset.

## Final Modelling Features

The final selected predictor set is:
1. Credit_History
2. Loan_Amount_Term
3. Is_Standard_Term
4. Income_to_LoanTerm_Interaction
5. Property_Area_Semiurban
6. Property_Area_Urban
7. Married
8. Education
9. Dependents

Target variable:
- Loan_Status (1 = Approved, 0 = Rejected)

## Key Deliverables

Processed datasets:
- data/processed/loan_prediction_cleaned.csv
- data/processed/loan_prediction_feature_engineered.csv
- data/processed/loan_prediction_ml_ready.csv
- data/processed/loan_prediction_refined_cleaned.csv
- data/processed/loan_prediction_refined_ml_ready.csv
- data/processed/final_modelling_dataset.csv

Reports:
- reports/Business Understanding Report Loan Eligibility Prediction.pdf
- reports/Data Preprocessing Report.pdf
- reports/Business_Insights_and_Recommendations_Report.pdf
- reports/Updated_Data_Dictionary.md

## How to Use This Repository

1. Start with notebooks/loan_approval_prediction.ipynb for preprocessing flow.
2. Review notebooks/advanced_eda_analysis_and_fe.ipynb for advanced analysis and feature engineering.
3. Use notebooks/feature_selection_evaluation.ipynb for feature selection logic and dataset refinement.
4. Train Week 4 models using data/processed/final_modelling_dataset.csv.

## Notes

- The refined dataset is intentionally parsimonious to improve stability and interpretability.
- Some engineered features were useful analytically but excluded from final modelling due to redundancy or weak incremental information gain.