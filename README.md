# PWC Power BI Virtual Work Experience - Customer Retention Analysis
![PwC Power BI Virtual Case Experience (1)](https://www.thealternativeboard.com/hubfs/Compressed-bigstock-Customer-Retention-Strategy-D-255195535.jpg)

## Table of Contents :

- [Problem Statement](https://github.com/mshukla94/Customer-Retention-Analysis/edit/main/README.md#problem-statement-)
- [Datasource](https://github.com/mshukla94/Customer-Retention-Analysis/edit/main/README.md#datasource-)
- [Data Preparation](https://github.com/mshukla94/Customer-Retention-Analysis/edit/main/README.md#data-preparation)
- [Data Modelling](https://github.com/mshukla94/Customer-Retention-Analysis/edit/main/README.md#data-modeling)
- [Data Analysis (DAX)](https://github.com/mshukla94/Customer-Retention-Analysis/edit/main/README.md#data-analysis-dax)
- [Data Visualization Dashboard](https://github.com/mshukla94/Customer-Retention-Analysis/edit/main/README.md#data-visualization-dashboard-)
- [Insights](https://github.com/mshukla94/Customer-Retention-Analysis/edit/main/README.md#insights-)


## Problem Statement :
In this project we need to define proper KPIs for the Retention Manager and then create a dashboard using those KPIs and metrics in the dataset. 


## Datasource :

Dataset used for this task was presented by [PwC](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html)

Customer Retention Dataset: [Customer Retention](https://github.com/mshukla94/Customer-Retention-Analysis/blob/main/02%20Churn-Dataset.xlsx)

## Data Preparation:

Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Customer Retention dataset is given table name:

- `Churn Dataset` which has `23 columns and 7043 rows` of observation

Data Cleaning for the dataset was done in the Power Query editor as follows:

- Removed Unnecessary columns
- Removed Unnecessary rows
- Each of the columns in the table were validated to have the correct data type

## Data Modeling:

The dataset was then cleaned and transformed, for it to be ready for data modeling.

- The `01 Churn-Dataset` tables as show below:

-![Data Structure](https://github.com/mshukla94/Customer-Retention-Analysis/blob/main/Churn%20Dataset.PNG)

## Data Analysis (DAX):

Measures used in visualization are defined as below:

- Churn Rate % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Churn]),'01 Churn-Dataset'[Churn]= "YES"),CALCULATE(COUNT('01 Churn-Dataset'[Churn]),ALLSELECTED('01 Churn-Dataset'[Churn])))`
  
- Count of device protection for Yes = `CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]), '01 Churn-Dataset'[DeviceProtection] = "YES")`

- Dependent in % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), '01 Churn-Dataset'[Dependents] = "yes", '01 Churn-Dataset'[Churn] = "yes"), CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "yes"),0)`

- Device Protection % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]), '01 Churn-Dataset'[DeviceProtection] = "yes", '01 Churn-Dataset'[Churn] = "yes"), CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "yes"),0)`

- MultipleLines % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]), '01 Churn-Dataset'[MultipleLines] = "yes", '01 Churn-Dataset'[Churn] = "yes"), CALCULATE(COUNT('01 Churn-Dataset'[MultipleLines]), '01 Churn-Dataset'[Churn] = "yes", '01 Churn-Dataset'[MultipleLines] <> "No phone service"),0)`

- Online Backup % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]), '01 Churn-Dataset'[OnlineBackup] = "yes", '01 Churn-Dataset'[Churn] = "yes"), CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "yes"),0)`

- Online Security % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]), '01 Churn-Dataset'[OnlineSecurity] = "yes", '01 Churn-Dataset'[Churn] = "yes"), CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "yes"),0)`

- Partner in % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Partner]), '01 Churn-Dataset'[Partner] = "yes", '01 Churn-Dataset'[Churn] = "yes"), CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn]= "yes"),0)`

- Phone Service % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]), '01 Churn-Dataset'[PhoneService] = "yes", '01 Churn-Dataset'[Churn] = "yes"), CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]), '01 Churn-Dataset'[Churn] = "yes"),0)`

- Senior Citizen in % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]), '01 Churn-Dataset'[SeniorCitizen]=1, '01 Churn-Dataset'[Churn] = "yes"), CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]), '01 Churn-Dataset'[Churn] = "yes"),0)`

- Streaming Movies % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]), '01 Churn-Dataset'[StreamingMovies] = "yes", '01 Churn-Dataset'[Churn] = "yes"), CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]), '01 Churn-Dataset'[Churn] = "yes"),0)`

- Streaming TV % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]), '01 Churn-Dataset'[StreamingTV] = "yes", '01 Churn-Dataset'[Churn] = "yes"), CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]), '01 Churn-Dataset'[Churn] = "yes"),0)`

- TechSupport % = `DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]), '01 Churn-Dataset'[TechSupport] = "yes", '01 Churn-Dataset'[Churn] = "yes"), CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]), '01 Churn-Dataset'[Churn] = "yes"),0)`


## Data Visualization (Dashboard) :

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

| Customer Retention (Overview) |
| ----------- |
| ![PWC Task - Customer Retention Dashboard](https://github.com/mshukla94/Customer-Retention-Analysis/blob/main/Churn%20Data%20Dashboard.PNG) |


## Insights :

As shown by Data Visualization, It can be deduced that:

- Total number of customers is 7043, out of which 1869 are at risk.
- Total revenue generated is $16.06M, out of which $2.86M is from the at-risk customers
- Of these 1869 customers, 88.55% are on month-to-month contracts, 8.88% on a one-year contract, and only 2.57% on a two-year contract
- Fiber optics is the most used internet service
- 74.91% of customers choose paperless billing and electronic check is the most used payment method

---

