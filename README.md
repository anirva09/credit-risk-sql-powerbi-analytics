# 💳 Credit Risk Analytics Dashboard

## PostgreSQL + SQL + Power BI

## 📌 Overview

This project analyzes loan portfolio data to identify borrower risk patterns, default behaviour, portfolio exposure, and credit risk factors.

The analysis was performed using **PostgreSQL** for data modeling and querying, while **Power BI** was used to create an interactive dashboard for risk monitoring and decision-making.

The dashboard helps answer questions such as:

- Which loan grades carry the highest risk?
- Which borrower groups are most likely to default?
- How does home ownership impact risk?
- Which loan purposes contribute the most exposure?
- What borrower characteristics influence default rates?

---

## 🧰 Tools Used

- PostgreSQL
- SQL
- Power BI
- DAX
- Data Modeling

---

## 🗂️ Data Model

The project follows a **Star Schema** design.

### 📌 Fact Table

- **loans**

### 📌 Dimension Tables

- **persons**
- **loan_grades**
- **loan_intents**
- **home_ownership**
- **credit_history**

---

## 📊 Power BI Dashboard Pages

### 1. Executive Overview

This page provides a high-level summary of the loan portfolio.

#### Key Metrics & Visuals

- Total Loans
- Total Exposure
- Average Loan Amount
- Average Interest Rate
- Total Defaults
- Default Rate
- Loan Grade Risk Analysis
- Portfolio Distribution by Loan Purpose
- Exposure at Risk by Loan Purpose

---

### 2. Risk Analytics & Default Behaviour

This page focuses on identifying major drivers of borrower defaults.

#### Key Metrics & Visuals

- Exposure at Risk
- Default Rate
- Credit History Risk Analysis
- Employment Length Risk Analysis
- Default Rate by Loan Purpose
- Borrower Risk Segmentation
- Home Ownership Risk Analysis

---

### 3. Customer Analytics

This page analyzes borrower demographics and financial profiles.

#### Key Metrics & Visuals

- Average Income
- Average Employment Length
- Average Credit History Length
- Average Loan-to-Income Ratio
- Age Group Analysis
- Income Distribution
- Income vs Default Analysis
- Loan-to-Income Risk Analysis
- Home Ownership Distribution

---

## 🖼️ Dashboard Screenshots

### Executive Overview

<img width="1323" height="761" alt="risk1" src="https://github.com/user-attachments/assets/26a778de-c967-4f81-918c-b063ccc5a713" />
<img width="1321" height="764" alt="risk2 0" src="https://github.com/user-attachments/assets/857c170d-18dd-46a2-b674-403180a71010" />

### Risk Analytics & Default Behaviour

<img width="1410" height="810" alt="risk2" src="https://github.com/user-attachments/assets/ce6ae06c-0369-4b31-9054-14c93b69c75b" />

### Customer Analytics

<img width="1413" height="810" alt="risk3" src="https://github.com/user-attachments/assets/779a1ce3-1654-4cda-a422-ca719d827f6e" />

---

## 🔍 Key Business Questions Answered

### ⚠️ Risk & Defaults

- Which loan grades have the highest default rates?
- Which loan purposes contribute most to risky exposure?
- Which borrower segments are classified as high risk?
- How does employment length affect default probability?

### 🏦 Portfolio Analysis

- What is the total portfolio exposure?
- What percentage of loans have defaulted?
- Which loan purposes dominate the portfolio?
- How is exposure distributed across borrower groups?

### 👥 Customer Analysis

- Which age groups take the most loans?
- How does income relate to default behaviour?
- Which income groups have higher loan-to-income ratios?
- How does home ownership vary across borrowers?

---

## 🧠 Key Insights

- Lower loan grades (**D–G**) show substantially higher default risk than higher grades.
- Debt Consolidation and Medical loans contribute a large portion of portfolio exposure.
- Borrowers with shorter employment histories exhibit higher default rates.
- Renters show significantly higher default rates compared to homeowners.
- Lower-income borrowers maintain higher loan-to-income ratios, increasing portfolio risk.
- The loan portfolio is concentrated in a few key loan purposes, creating exposure concentration risk.

---

## 🧠 Key Learnings

- Designed a Star Schema model for financial analytics.
- Built KPI-driven dashboards for credit risk monitoring.
- Used SQL to prepare and structure analytical datasets.
- Created DAX measures for portfolio exposure, defaults, and risk segmentation.
- Applied business intelligence principles to analyze borrower behaviour.
- Developed multi-page dashboards focused on executive reporting and risk analysis.

---

## 📌 Important DAX Measures

### Total Loans

```DAX
Total Loans =
COUNT(loans[loan_id])
```

### Total Exposure

```DAX
Total Exposure =
SUM(loans[loan_amnt])
```

### Default Rate

```DAX
Default Rate =
DIVIDE(
    [Total Defaults],
    [Total Loans]
)
```

### Total Defaults

```DAX
Total Defaults =
CALCULATE(
    COUNT(loans[loan_id]),
    loans[loan_status] = "Default"
)
```

### Average Interest Rate

```DAX
Average Interest Rate =
AVERAGE(loans[loan_int_rate])
```

### Exposure At Risk

```DAX
Exposure At Risk =
CALCULATE(
    SUM(loans[loan_amnt]),
    loans[loan_status] = "Default"
)
```

---

## 🚀 Future Improvements

- Predictive Default Risk Scoring
- Machine Learning-Based Credit Risk Models
- Probability of Default (PD) Analysis
- Loss Given Default (LGD) Metrics
- Time-Series Default Trend Analysis
- Drillthrough Risk Investigation Pages
- Power BI Service Deployment

---


## ✅ Conclusion

This project demonstrates an end-to-end credit risk analytics workflow using **PostgreSQL, SQL, Power BI, and DAX**. The dashboard provides actionable insights into portfolio performance, borrower risk behaviour, default trends, and exposure management, helping financial institutions make more informed lending decisions.

---
