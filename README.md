<div align="center">

# 📊 Customer Churn Risk Analysis Dashboard

### Interactive Power BI dashboard for identifying, scoring, and tracking customer churn risk

<img src="https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black"/>
<img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"/>
<img src="https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white"/>
<img src="https://img.shields.io/badge/DAX-8a2be2?style=for-the-badge"/>

</div>

---

## 📌 Overview

This dashboard analyzes customer behavior data to flag accounts at risk of churn, quantify what's driving that risk, and give stakeholders a single view to prioritize retention efforts. It combines KPI tracking, segmentation, and a churn-risk scoring model surfaced through interactive Power BI visuals.

---

## ✨ Features

- **Churn Risk Scoring** — customers segmented into Low / Medium / High risk bands based on behavioral and account signals
- **KPI Tracking** — churn rate, retention rate, average customer tenure, revenue at risk
- **Driver Analysis** — breakdown of churn by contract type, tenure, usage patterns, support tickets, and payment method
- **Cohort & Trend Views** — churn rate over time, cohort retention curves
- **Interactive Filtering** — slicers for region, plan type, tenure band, and risk tier
- **Drill-Through** — from summary KPIs down to individual customer-level detail

---

## 🗂️ Dashboard Pages

| Page | Purpose |
|---|---|
| Overview | High-level KPIs and churn rate trend |
| Risk Segmentation | Customers grouped by churn risk tier with contributing factors |
| Driver Analysis | Churn broken down by key dimensions (contract, tenure, usage, support) |
| Customer Detail | Drill-through view for individual account investigation |

---

## 🧮 Sample DAX Measures

```dax
Churn Rate =
DIVIDE(
    CALCULATE(COUNTROWS(Customers), Customers[Churned] = TRUE()),
    COUNTROWS(Customers)
)

Revenue at Risk =
CALCULATE(
    SUM(Customers[MonthlyCharges]),
    Customers[RiskTier] = "High"
)

Risk Tier =
SWITCH(
    TRUE(),
    [Churn Probability] >= 0.7, "High",
    [Churn Probability] >= 0.4, "Medium",
    "Low"
)
```

---

## 🛠️ Tech Stack

- **Power BI** — dashboard design, DAX measures, data modeling
- **SQL** — source data extraction and transformation
- **Excel** — data cleaning and validation

---

## 🖼️ Screenshots

> _Add dashboard screenshots here, e.g._
> `![Overview Page](screenshots/overview.png)`

---

## 🚀 How to Use

1. Clone this repository
2. Open `ChurnRiskDashboard.pbix` in Power BI Desktop
3. Update the data source connection to point to your dataset
4. Refresh the model to load your data
5. Explore via the slicers and drill-through pages

---

## 📈 Key Insights

> _Summarize 2–3 concrete findings once your analysis is finalized, e.g. which segment has the highest churn risk and what's driving it._

---

## 📄 License

This project is open for learning and portfolio reference. Feel free to fork and adapt.
