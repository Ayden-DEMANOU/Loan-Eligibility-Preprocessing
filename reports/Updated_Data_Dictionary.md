# Updated Data Dictionary

This data dictionary reflects the final refined outputs produced in Part 6 and used for Week 4:
- loan_prediction_refined_cleaned.csv
- final_modelling_dataset.csv

## Dataset-Level Metadata

| Item | Value |
|---|---|
| Primary analytical dataset | loan_prediction_refined_cleaned.csv |
| Primary modelling dataset | final_modelling_dataset.csv |
| Number of rows | 614 |
| Number of columns | 10 |
| Target variable | Loan_Status |
| Scaling method in modelling file | RobustScaler (applied only to Loan_Amount_Term and Income_to_LoanTerm_Interaction) |
| Leakage status | No direct target leakage in retained features |

## Column Dictionary

| Column Name | Data Type (Cleaned) | Data Type (Modelling) | Role | Definition | Encoding / Values | Transformation Applied | Business Meaning |
|---|---|---|---|---|---|---|---|
| Credit_History | int | int | Predictor | Applicant credit history indicator | 1 = good history, 0 = poor/no history | None | Core proxy for repayment discipline and default risk |
| Loan_Amount_Term | int | float | Predictor | Loan repayment duration in months | Common values include 360, 180, 120, etc. | RobustScaler in modelling file | Captures contractual repayment horizon |
| Is_Standard_Term | int | int | Engineered Predictor | Flag for standard term structure | 1 = 360 months, 0 = non-standard term | Engineered from Loan_Amount_Term | Encodes policy/product norm and deviation risk |
| Income_to_LoanTerm_Interaction | float | float | Engineered Predictor | Interaction of income capacity and term length | Continuous numeric | Computed as Total_Income x Loan_Amount_Term; then RobustScaler in modelling file | Captures affordability context jointly with term structure |
| Property_Area_Semiurban | int | int | Predictor | One-hot flag for Semiurban property area | 1 = Semiurban, 0 = otherwise | One-hot encoding | Geography-based profile and market behavior signal |
| Property_Area_Urban | int | int | Predictor | One-hot flag for Urban property area | 1 = Urban, 0 = otherwise | One-hot encoding | Geography-based profile and market behavior signal |
| Married | int | int | Predictor | Marital status indicator | 1 = Yes, 0 = No | Binary encoding | Household profile feature linked to repayment context |
| Education | int | int | Predictor | Education status indicator | 1 = Graduate, 0 = Not Graduate | Binary encoding | Socio-economic profile related to borrowing patterns |
| Dependents | int | int | Predictor | Number of dependents | 0, 1, 2, 3 | Cleaned and cast to integer | Household financial burden indicator |
| Loan_Status | int | int | Target | Loan approval outcome | 1 = Approved, 0 = Rejected | Target mapping from Y/N to 1/0 | Supervised learning target for approval prediction |

## Notes on Removed Features

The following variables were removed from the refined modelling set due to low mutual information, high redundancy, or multicollinearity concerns:
- Loan_Term_Years
- Total_Income
- Log_Total_Income
- Loan_Income_Ratio
- Repayment_Risk_Category
- Repayment_Burden_Pct
- Income_Band
- Income_Per_Person
- Gender
- Self_Employed
- Monthly_Repayment
- Credit_Profile_Segment

## Usage Guidance for Week 4

- Use loan_prediction_refined_cleaned.csv for interpretation, diagnostics, and business reporting.
- Use final_modelling_dataset.csv for model training and cross-validation.
- Do not re-scale binary or one-hot columns.
- If model family is highly scale-sensitive, keep the current robust-scaled numerical variables as provided.
