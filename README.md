# 📊 Customer Churn Analysis Using Power BI

---

## 📖 Introduction
Customer churn — the rate at which customers stop doing business with a service provider — is a critical performance indicator in telecom, finance, and SaaS industries.  

This Power BI project analyzes **customer churn from 2020 to 2025** using interactive dashboards, DAX measures, and a custom date table. The goal was to uncover patterns in client attrition and identify actionable factors for improving retention strategies.

---

## 🔗 Live Dashboard
👉 [View the interactive dashboard on Power BI Service](https://app.powerbi.com/view?r=YOUR-LINK-HERE)

*(Note: The report is published online for interactive exploration. Please allow time for it to load.)*

---

## 🛠️ Tools & Skills
- **Power BI**: Data modeling, relationships, slicers, interactive visuals  
- **DAX**: Custom measures for churn count, churn rate, rolling averages  
- **Data Modeling**: Dedicated date table with year, month, and quarter for accurate time-series analysis  
- **Visualization**: KPI cards, bar charts, combo charts, scatter plots, line charts  

---

## 📊 Dashboard Highlights

- **KPI Gauge (Churn Count)**  
  Shows **483 churned clients**, highlighting a high attrition rate.  

- **Bar Chart (Client Distribution by Data Usage)**  
  Reveals most churned clients had **low data usage**.  

- **Combo Chart (Service Calls vs. Churn Rate)**  
  Churn rate spikes with **5+ service calls**, suggesting dissatisfaction with support.  

- **Scatter Plot (Data Usage vs. Monthly Charges)**  
  Churned customers cluster in **low usage & low charge** segments.  

- **Line Chart (Churn Over Time)**  
  Churn peaked in **2022** and declined afterward, possibly due to retention programs.  

---

## 📐 DAX Implementation
```DAX
-- Churned Customers
Churn Count =
CALCULATE (
    COUNTROWS('Customer Churn'),
    'Customer Churn'[Churn] = 1
)

-- Churn Rate
Churn Rate =
DIVIDE (
    CALCULATE ( COUNTROWS('Customer Churn'), 'Customer Churn'[Churn] = 1 ),
    COUNTROWS('Customer Churn')
)
