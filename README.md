# Loan Approval Preprocessing & Feature Engineering Pipeline

**Author:** Ayden Demanou | Junior Data Scientist | AnalystLab Africa Consulting  
**Client:** Retail Financial Services Division  
**Project:** Automated Loan Eligibility Risk Scoring System  
**Dataset:** [Kaggle Loan Prediction Problem Dataset](https://www.kaggle.com/datasets/altruistdelhite04/loan-prediction-problem-dataset)  

---

## Executive Summary
This repository contains the end-to-end data preprocessing, missing value imputation, domain feature engineering, categorical encoding, and scaling pipeline for retail loan applications. 

The primary business objective is to transform raw, unstructured loan applicant data into a clean, machine-learning-ready format suitable for training predictive classifiers. By automating the credit evaluation workflow, the financial institution aims to accelerate loan turnaround times, eliminate subjective underwriting bias, and reduce Non-Performing Loans (NPLs).

---

## Directory Structure

```text
loan-eligibility-preprocessing/
│
├── .gitignore                          # Git ignore rules for cache & local envs
├── README.md                           # Master project documentation
├── requirements.txt                    # Project dependencies for reproducibility
│
├── data/
│   ├── raw/
│   │   └── train_u6lujuX_CVtuZ9i.csv   # Original un-preprocessed training dataset
│   └── processed/
│       └── loan_prediction_ml_ready.csv# Final scaled, encoded & ML-ready dataset
│
├── notebooks/
│   └── Loan_approval_prediction.ipynb # Executed Jupyter Notebook with complete workflow
│
├── reports/
│   ├── Business Understanding Report Loan Eligibility Prediction.pdf # Executive business understanding memo
│   └── Data Preprocessing Report.pdf # Technical preprocessing documentation
│
└── charts/

## Features Explained

A. Loan Income Ratio
**What is Loan_Income_Ratio?** It is a ratio that compares the loan amount an applicant is seeking (or has) to their total income.
**Why is it important in loan decisions?** This ratio is a direct measure of an applicant's debt burden relative to their financial capacity. It helps lenders assess:

1. Affordability: A lower Loan_Income_Ratio suggests that the applicant's income can comfortably cover the loan repayment, leaving them with sufficient funds for other expenses.
2. Risk Assessment: A higher ratio indicates a greater financial strain on the applicant. It means they are asking for a loan that represents a significant portion of their income, which increases the risk of default.
3. Comparative Analysis: Two applicants with the same loan amount but vastly different incomes pose different levels of risk. This ratio normalizes the loan amount against income, providing a more accurate picture of their ability to manage the debt.
In essence, Loan_Income_Ratio helps determine if the loan amount requested is sustainable for the applicant given their earning power.

B. Credit History

**What is Credit_History?** In this dataset, Credit_History typically represents whether an applicant has met their past credit obligations. It's often a binary variable:
1: Indicates a good credit history, meaning the applicant has generally repaid their previous debts on time and as agreed.
0: Indicates a poor credit history, suggesting past defaults, late payments, or no credit history at all.

**Why is it important in loan decisions?** Credit_History is a strong indicator of an applicant's reliability and willingness to repay debt. Lenders use it to gauge future behavior based on past performance:

* Predictor of Default: Applicants with a good credit history are statistically less likely to default on new loans. Conversely, a poor credit history signals a higher risk.
* Trust and Credibility: It establishes trust. A long history of responsible credit use tells a lender that the applicant is a credible borrower.
* Risk Mitigation: Lenders use credit history to mitigate their risk. They are more inclined to lend to individuals with proven repayment capabilities.
* Foundation of Financial Reputation: It's essentially an applicant's financial report card, reflecting their past handling of borrowed money.
As we saw in the Chi-square test, Credit_History had a highly significant relationship with Loan_Status, demonstrating its paramount importance in loan approval decisions.