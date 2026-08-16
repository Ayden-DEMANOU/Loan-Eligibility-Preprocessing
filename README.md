# Loan Approval Preprocessing & Feature Engineering Pipeline

**Author:** Junior Data Scientist | AnalystLab Africa Consulting  
**Client:** Retail Financial Services Division  
**Project:** Automated Loan Eligibility Risk Scoring System  
**Dataset:** [Kaggle Loan Prediction Problem Dataset](https://www.kaggle.com/datasets/altruistdelhite04/loan-prediction-problem-dataset)  

---

## Executive Summary
This repository contains the end-to-end data preprocessing, missing value imputation, domain feature engineering, categorical encoding, and scaling pipeline for retail loan applications. 

The primary business objective is to transform raw, unstructured loan applicant data into a clean, machine-learning-ready format suitable for training predictive classifiers in Week 3. By automating the credit evaluation workflow, the financial institution aims to accelerate loan turnaround times, eliminate subjective underwriting bias, and reduce Non-Performing Loans (NPLs).

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