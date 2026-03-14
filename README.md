# Credit Risk Modeling – PD Estimation and Credit Limit Optimization

## Overview

This project presents an end-to-end credit risk modeling pipeline developed in **R**.
The objective is to estimate the **Probability of Default (PD)** for loan applicants and use this information to support **credit approval decisions and credit limit assignment**.

The project includes exploratory data analysis, predictive modeling, model evaluation, probability calibration, and a framework for **risk-based lending strategies**.

---

## Key Results

* **Model:** Random Forest
* **AUC:** 0.84
* **KS Statistic:** 0.42
* **Brier Score:** 0.17

These metrics indicate the model’s ability to discriminate between default and non-default borrowers and the calibration quality of predicted probabilities.

---

## Business Impact

The predicted **Probability of Default (PD)** is used to support lending decisions and evaluate the financial performance of different credit strategies.

The analysis compares the current lending policy with a strategy based on **risk-adjusted credit limits and approval rules derived from the PD model**.

### Portfolio Results

| Strategy                             | Expected Profit |
| ------------------------------------ | --------------- |
| Current policy                       | 8,863,944       |
| Optimized credit limits              | 37,019,335      |
| Optimized policy with rejection rule | 37,028,362      |

The optimized strategy increases portfolio profitability by **more than four times compared to the current policy**, illustrating the potential value of integrating machine learning models into credit decision processes.

### Risk and Business Metrics

* **Expected Return on Assets (ROA):** 0.448
* **Expected Loss Rate:** 0.143
* **Approval Rate:** 0.995

These metrics illustrate how the PD model can be integrated with **credit limit optimization and approval policies** to balance profitability and credit risk in a lending portfolio.

---

## Credit Risk Framework

Credit risk in lending portfolios is commonly evaluated using the **Expected Loss (EL)** framework:

**EL = PD × LGD × EAD**

Where:

* **PD (Probability of Default):** probability that a borrower defaults on the loan
* **LGD (Loss Given Default):** proportion of the exposure that is lost if a default occurs
* **EAD (Exposure at Default):** total exposure at the time of default

In this project:

* **PD** is estimated using a **Random Forest model**
* **EAD** corresponds to the granted credit exposure (loan amount or credit limit)
* **Expected Loss (EL)** is computed for each borrower to evaluate portfolio risk and expected financial impact

This framework links the **machine learning model** to financial risk metrics used in credit risk management.

---

## Dataset

Dataset source:
https://www.kaggle.com/datasets/laotse/credit-risk-dataset

A mirrored version of the dataset can also be found in several GitHub repositories used for machine learning projects.

---

The analysis uses the **Credit Risk Dataset**, which contains borrower characteristics and loan information used to model credit default risk.

The dataset includes approximately **32,581 observations** and the following main variables:

* **person_age** – Borrower's age
* **person_income** – Annual income of the borrower
* **person_home_ownership** – Home ownership status
* **person_emp_length** – Employment length (in years)
* **loan_intent** – Purpose of the loan
* **loan_grade** – Credit grade assigned to the loan
* **loan_amnt** – Loan amount
* **loan_int_rate** – Interest rate of the loan
* **loan_percent_income** – Loan amount as a percentage of income
* **cb_person_default_on_file** – Historical default indicator
* **cb_person_cred_hist_length** – Length of credit history

The target variable is:

**loan_status**

* `1` → Default
* `0` → Non-default

---

## Project Workflow

### 1. Exploratory Data Analysis

Initial exploration of the dataset including:

* Distribution of loan purposes
* Home ownership categories
* Loan grades
* Default history

This step helps understand borrower profiles and potential risk patterns.

---

### 2. Data Preparation

Key preprocessing steps include:

* Handling categorical variables
* Converting variables to appropriate types
* Splitting the data into **training and testing sets**
* Feature selection

---

### 3. Probability of Default (PD) Model

A **Random Forest classifier** is used to estimate the probability that a borrower will default.

The model outputs:

* Predicted class (default / non-default)
* **Probability of Default (PD)** for each borrower

---

### 4. Model Evaluation

Model performance is evaluated using several metrics commonly used in credit risk modeling:

* **ROC Curve**
* **AUC (Area Under the Curve)**
* **KS Statistic**
* **Brier Score**

These metrics measure the model’s ability to distinguish between default and non-default borrowers.

---

### 5. Probability Calibration

Predicted probabilities are calibrated using **Platt Scaling** to improve the reliability of PD estimates.

Calibration ensures that predicted probabilities better match the observed default frequencies.

---

### 6. Risk-Based Credit Decisions

The calibrated PD is used to support credit decisions, including:

* Credit approval or rejection
* Credit limit assignment
* Expected loss estimation

This creates a simple framework for **risk-based pricing and credit limit optimization**.

---

## Technologies Used

* **R**
* Random Forest
* Data manipulation and visualization packages
* Statistical evaluation metrics for classification models
* tidyverse
* ggplot2
* pROC
* caret
---

## Project Structure

```
credit-risk-model/
│
├── Credit-Risk-Project.html   # Full project report
├── README.md                  # Project description
└── scripts/                   # (optional) R scripts
```

---

## Author

**Guilherme Henrique Hispagnol Bicho**

---

## Purpose of the Project

This project was developed as a **portfolio project in credit risk modeling and applied machine learning**, demonstrating the use of statistical and machine learning techniques to support lending decisions.
