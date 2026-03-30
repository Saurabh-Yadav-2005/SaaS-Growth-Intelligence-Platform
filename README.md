# SaaS Growth Intelligence Platform

An end-to-end data analytics project simulating a real-world SaaS business intelligence workflow — from raw data ingestion to an executive Power BI dashboard.

---

## Project Overview

This project analyzes **RavenStack**, a fictional SaaS startup, using 5 interconnected datasets covering accounts, subscriptions, feature usage, support tickets, and churn events. The goal was to uncover what drives customer churn, forecast future revenue, and present findings in an executive-level dashboard.

---

## Architecture

```
Raw CSV Files (32,100+ rows)
        ↓
Python ETL Pipeline (Pandas + SQLAlchemy)
        ↓
SQLite Database (7 tables)
        ↓
Machine Learning Models (XGBoost + Prophet)
        ↓
Power BI Executive Dashboard (3 pages)
```

---

## Project Structure

```
saas-growth-platform/
│
├── data_set/                          # Raw CSV files
│   ├── ravenstack_accounts.csv
│   ├── ravenstack_subscriptions.csv
│   ├── ravenstack_churn_events.csv
│   ├── ravenstack_feature_usage.csv
│   └── ravenstack_support_tickets.csv
│
├── notebook/                          # Jupyter notebooks
│   ├── 01_etl_cleaning.ipynb          # Phase 1 - ETL Pipeline
│   ├── 02_churn_model.ipynb           # Phase 2 - Churn Prediction
│   ├── 03_mrr_forecast.ipynb          # Phase 3 - MRR Forecasting
│   └── 04_export_for_powerbi.ipynb    # Phase 4 - Power BI Export
│
├── database/
│   └── saas_data.db                   # SQLite database
│
├── powerbi/
│   └── SaaS_Growth_Intelligence_Platform.pbix
│
└── README.md
```

---

## Phase 1 — ETL Data Pipeline

**Tools:** Python, Pandas, SQLAlchemy, SQLite

- Ingested 5 raw CSV files containing 32,100+ rows of SaaS data
- Performed data cleaning — handled missing values, fixed date formats, removed duplicates
- Engineered new features: subscription duration, resolution categories, usage duration in minutes
- Loaded all cleaned tables into a normalized SQLite database

**Key stats after cleaning:**

| Table | Rows |
|---|---|
| accounts | 500 |
| subscriptions | 5,000 |
| feature_usage | 25,000 |
| support_tickets | 2,000 |
| churn_events | 600 |

---

## Phase 2 — Churn Prediction Model

**Tools:** Python, XGBoost, Scikit-learn, SHAP, Pandas

- Engineered 19 features from 5 tables including RFM-style metrics, support ticket history, and feature usage patterns
- Trained an XGBoost classifier to predict customer churn probability
- Evaluated model performance using ROC-AUC score and classification report
- Saved churn probability scores and risk labels (High / Medium / Low) back to the database

**Model Performance:**

| Metric | Score |
|---|---|
| ROC-AUC | 0.82 |
| Features Used | 19 |
| Training Set | 400 accounts |
| Test Set | 100 accounts |

**Top churn drivers identified:**
- Plan downgrades within 90 days
- High support ticket escalation rate
- Low feature usage frequency
- Short subscription duration

---

## Phase 3 — MRR Forecasting

**Tools:** Python, Facebook Prophet, Scikit-learn, Matplotlib

- Built a monthly MRR time series from subscription data
- Trained a Facebook Prophet model with yearly seasonality
- Evaluated accuracy using MAPE score on held-out test months
- Generated a 6-month forward revenue forecast with confidence intervals
- Saved forecast results to the database for Power BI integration

**Model Performance:**

| Metric | Score |
|---|---|
| Forecasting Model | Facebook Prophet |
| Forecast Horizon | 6 months |
| Seasonality | Yearly multiplicative |

---

## Phase 4 — Power BI Executive Dashboard

**Tools:** Power BI Desktop, DAX

3-page interactive dashboard connected to the SQLite database:

**Page 1 — SaaS Growth Overview**
- Total MRR, Total Accounts, Churn Rate, Avg Satisfaction KPI cards
- Churn by Plan Tier bar chart
- Churn Risk Distribution pie chart

**Page 2 — Churn Risk Analysis**
- Customer churn risk table with probability scores
- Churn reasons breakdown bar chart
- Churn by industry pie chart

**Page 3 — MRR Revenue Forecast**
- 6-month MRR forecast line chart with confidence bands
- MRR by plan tier breakdown
- Average forecast MRR card

---

## Tech Stack

| Category | Tools |
|---|---|
| Data Processing | Python, Pandas, NumPy |
| Database | SQLite, SQLAlchemy |
| Machine Learning | XGBoost, Scikit-learn, SHAP |
| Forecasting | Facebook Prophet |
| Visualization | Matplotlib, Seaborn, Power BI |
| Environment | Jupyter Notebook |
| Version Control | Git, GitHub |

---

## Key Business Insights

- Customers on the **Basic plan** have the highest churn rate
- **Pricing** is the most common churn reason, followed by support issues
- Accounts with **high support ticket escalations** are 3x more likely to churn
- MRR shows a **steady growth trend** with projected increase over the next 6 months

---

## Dataset Credit

Dataset: **RavenStack Synthetic SaaS Dataset** by River @ Rivalytics
License: MIT-like (fully synthetic, no PII)
Source: [Kaggle](https://www.kaggle.com/datasets/rivalytics/saas-subscription-and-churn-analytics-dataset)

---

## Author

**Saurabh Yadav**
Data Analyst | Python | SQL | Power BI | Machine Learning
