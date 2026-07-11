# Credit Risk Analytics Dashboard

A PostgreSQL, SQL and Power BI-based financial analytics project built to analyse loan portfolio exposure, borrower risk behaviour, default patterns, loan grade performance, credit history, home ownership risk and customer financial profiles.

---

## Project Overview

This project presents an end-to-end **Credit Risk Analytics Dashboard** using **PostgreSQL, SQL, Power BI and DAX**.

The project analyses loan portfolio data to identify borrower risk patterns, default behaviour, portfolio exposure and key credit risk factors. PostgreSQL was used for data modelling and querying, while Power BI was used to build an interactive dashboard for risk monitoring and decision-making.

The dashboard helps understand loan grade risk, borrower segmentation, default drivers, exposure concentration, customer financial behaviour and portfolio-level credit risk.

---

## Business Problem

Financial institutions need to monitor loan portfolios continuously because borrower repayment behaviour, default risk, income levels, employment history, loan purpose and credit history can strongly influence portfolio performance.

A credit risk or lending analytics team needs to answer questions such as:

* Which loan grades carry the highest default risk?
* Which borrower groups are more likely to default?
* Which loan purposes contribute the most risky exposure?
* How does home ownership affect borrower risk?
* How does income influence loan-to-income risk?
* Which customer segments require closer monitoring?

This project solves the problem by creating a structured credit risk analytics workflow using PostgreSQL for data modelling and Power BI for dashboard reporting.

---

## Tools Used

| Tool           | Purpose                                        |
| -------------- | ---------------------------------------------- |
| PostgreSQL     | Database creation, data modelling and querying |
| SQL            | Business analysis and data extraction          |
| Power BI       | Dashboard development and visual analytics     |
| DAX            | Metric calculation and business logic          |
| Data Modelling | Star schema design for analytical reporting    |

---

## Data Model Summary

The project follows a **Star Schema** design to organise loan portfolio data for financial analytics.

| Table            | Type            | Purpose                                                                              |
| ---------------- | --------------- | ------------------------------------------------------------------------------------ |
| `loans`          | Fact Table      | Stores loan amount, interest rate, loan status, borrower keys and portfolio exposure |
| `persons`        | Dimension Table | Stores borrower demographic and financial attributes                                 |
| `loan_grades`    | Dimension Table | Stores loan grade and credit quality information                                     |
| `loan_intents`   | Dimension Table | Stores loan purpose or intent categories                                             |
| `home_ownership` | Dimension Table | Stores borrower home ownership status                                                |
| `credit_history` | Dimension Table | Stores borrower credit history length and related attributes                         |

This model supports cleaner analysis across borrower profile, loan grade, loan purpose, home ownership and credit history dimensions.

---

## Dashboard Modules

| Page | Module                             | Focus                                                              |
| ---- | ---------------------------------- | ------------------------------------------------------------------ |
| 1    | Executive Overview                 | High-level loan portfolio performance and credit risk summary      |
| 2    | Risk Analytics & Default Behaviour | Default drivers, risky exposure and borrower risk segmentation     |
| 3    | Customer Analytics                 | Borrower demographics, income profile and loan-to-income behaviour |

---

## Dashboard Preview

### Executive Overview

<img width="1323" height="764" alt="risk1" src="https://github.com/user-attachments/assets/d78d0fe1-c704-42e3-816a-bfce2da0b42d" />

### Risk Analytics & Default Behaviour

<img width="1320" height="765" alt="RISK2" src="https://github.com/user-attachments/assets/0a0511f2-39ef-4f5f-b506-463f91650a63" />

### Customer Analytics

<img width="1322" height="765" alt="RISK3" src="https://github.com/user-attachments/assets/fea57446-6904-4918-8ac0-f8c333d3b8c2" />

---

## Key Metrics Tracked

| Area                  | Metrics                                                                  |
| --------------------- | ------------------------------------------------------------------------ |
| Portfolio Performance | Total Loans, Total Exposure, Average Loan Amount, Average Interest Rate  |
| Default Monitoring    | Total Defaults, Default Rate, Exposure at Risk                           |
| Loan Grade Risk       | Default Rate by Loan Grade, Exposure by Loan Grade                       |
| Loan Purpose Analysis | Portfolio Distribution by Loan Purpose, Exposure at Risk by Loan Purpose |
| Borrower Risk         | Employment Length Risk, Credit History Risk, Home Ownership Risk         |
| Customer Analytics    | Average Income, Average Employment Length, Average Credit History Length |
| Affordability Risk    | Average Loan-to-Income Ratio, Income vs Default Analysis                 |

---

## Key Business Questions Answered

### Risk & Defaults

* Which loan grades have the highest default rates?
* Which loan purposes contribute most to risky exposure?
* Which borrower segments are classified as high risk?
* How does employment length affect default probability?

### Portfolio Analysis

* What is the total portfolio exposure?
* What percentage of loans have defaulted?
* Which loan purposes dominate the portfolio?
* How is exposure distributed across borrower groups?

### Customer Analysis

* Which age groups take the most loans?
* How does income relate to default behaviour?
* Which income groups have higher loan-to-income ratios?
* How does home ownership vary across borrowers?

---

## SQL Analysis Workflow

PostgreSQL and SQL were used to structure the data and support business analysis before dashboard creation.

The SQL workflow included:

* Creating a star schema using fact and dimension tables
* Joining borrower, loan, grade, intent, home ownership and credit history data
* Calculating portfolio exposure and default counts
* Analysing default rate by loan grade
* Analysing exposure by loan purpose
* Studying borrower risk based on employment length and home ownership
* Preparing clean analytical outputs for Power BI reporting

This helped ensure that the Power BI dashboard was based on structured and query-ready data.

---

## Important DAX Measures

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

### Total Defaults

```DAX
Total Defaults =
CALCULATE(
    COUNT(loans[loan_id]),
    loans[loan_status] = "Default"
)
```

### Default Rate

```DAX
Default Rate =
DIVIDE(
    [Total Defaults],
    [Total Loans]
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

## Key Insights

* Lower loan grades such as **D–G** show higher default risk compared to stronger grades.
* Debt consolidation and medical loans contribute significantly to portfolio exposure.
* Borrowers with shorter employment histories show higher default tendencies.
* Renters show higher default rates compared to homeowners.
* Lower-income borrowers tend to carry higher loan-to-income ratios, increasing affordability risk.
* Portfolio exposure is concentrated in selected loan purposes, creating concentration risk.
* Credit history, employment length and home ownership are important borrower risk indicators.

---

## Project Outputs

| Output                | Description                                                                    |
| --------------------- | ------------------------------------------------------------------------------ |
| PostgreSQL Database   | Structured database using fact and dimension tables                            |
| SQL Analysis          | Queries used to analyse portfolio exposure, defaults and borrower risk         |
| Power BI Dashboard    | Interactive dashboard covering executive, risk and customer analytics          |
| DAX Measures          | Measures for exposure, defaults, interest rate, default rate and risk analysis |
| Dashboard Screenshots | Dashboard page screenshots for portfolio presentation                          |
| Documentation         | README and project explanation for GitHub portfolio                            |

---

## Assumptions and Limitations

* The dataset is used for educational and portfolio purposes.
* The project focuses on descriptive credit risk analytics, not predictive modelling.
* Default status is treated based on the available loan status field.
* Exposure at risk is calculated using defaulted loan exposure.
* The dashboard does not include PD, LGD or EAD modelling.
* The project does not include machine learning-based default prediction.
* The analysis is based on available borrower, loan, grade, intent, home ownership and credit history fields.

---

## Skills Demonstrated

* PostgreSQL database design
* SQL querying and analysis
* Star schema data modelling
* Power BI dashboard development
* DAX measure creation
* Credit risk analytics
* Loan portfolio analysis
* Default behaviour analysis
* Customer segmentation
* Financial analytics reporting
* Business insight communication

---

## Future Improvements

* Add predictive default risk scoring.
* Build machine learning-based credit risk models.
* Add Probability of Default (PD) and Loss Given Default (LGD) metrics.
* Add time-series default trend analysis.
* Create drillthrough pages for borrower-level risk investigation.
* Include collections and recovery data.
* Deploy the dashboard using Power BI Service.

---

## Project Positioning

This project demonstrates an end-to-end credit risk analytics workflow using PostgreSQL, SQL, Power BI and DAX. It combines data modelling, query-based analysis, dashboard development and business interpretation to present a professional financial analytics portfolio project.

---

## Author

**Anirva Manchikatla**
B.Tech CSE | Data Analytics | Business Intelligence | Credit Risk Analytics
