#  SaaS Growth Intelligence Platform

A full-stack data analytics project simulating how real SaaS companies track growth, predict customer churn, and forecast revenue using machine learning and business intelligence tools.

 Built to answer one core question:
**Why do customers churn — and how can we predict it before it happens?**

---

##  Project Overview

This project analyzes **RavenStack**, a fictional SaaS startup, using 5 interconnected datasets covering:

* Customer accounts
* Subscriptions
* Feature usage
* Support tickets
* Churn events

The goal is to:

* Identify key drivers of churn
* Predict high-risk customers
* Forecast future revenue (MRR)
* Deliver insights through an executive dashboard

---

##  Architecture

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

##  Project Structure

```
saas-growth-platform/
│
├── data_set/                          
├── notebook/                          
├── database/                          
├── powerbi/                           
├── assets/                # Dashboard screenshots
├── requirements.txt       
├── .gitignore             
└── README.md
```

---

##  How to Run

1. Clone the repository

```
git clone https://github.com/your-username/saas-growth-platform.git
```

2. Install dependencies

```
pip install -r requirements.txt
```

3. Run notebooks in order:

* 01_etl_cleaning.ipynb
* 02_churn_model.ipynb
* 03_mrr_forecast.ipynb
* 04_export_for_powerbi.ipynb

4. Open Power BI dashboard:

```
powerbi/SaaS_Growth_Intelligence_Platform.pbix
```

---

##  Dashboard Preview

*(Add screenshots in the /assets folder and update paths below)*

```
assets/dashboard1.png
assets/dashboard2.png
assets/dashboard3.png
```

---

## Key Features

* End-to-end ETL pipeline for multi-source SaaS data
* Churn prediction using XGBoost (ROC-AUC: 0.82)
* Feature engineering across relational datasets
* Revenue forecasting using Facebook Prophet
* Interactive Power BI dashboard for decision-making

---

##  Machine Learning Models

### Churn Prediction

* Model: XGBoost Classifier
* Features: 19 engineered features
* Evaluation: ROC-AUC = 0.82

### Revenue Forecasting

* Model: Facebook Prophet
* Forecast Horizon: 6 months
* Seasonality: Yearly

---

##  Business Impact

* Identified high-risk customers before churn → enables proactive retention
* Highlighted key churn drivers like pricing and support issues
* Improved revenue planning with 6-month MRR forecast
* Delivered executive-level insights via interactive dashboard

---

## Key Insights

* Basic plan users show the highest churn rate
* Pricing is the top churn reason
* High support ticket escalation → 3x higher churn probability
* Revenue trend shows consistent projected growth

---

##  Key Learnings

* End-to-end data pipeline design (ETL → ML → BI)
* Feature engineering across multiple datasets
* Model interpretability using SHAP
* Translating data into business insights

---

##  Tech Stack

| Category         | Tools                         |
| ---------------- | ----------------------------- |
| Data Processing  | Python, Pandas, NumPy         |
| Database         | SQLite, SQLAlchemy            |
| Machine Learning | XGBoost, Scikit-learn, SHAP   |
| Forecasting      | Facebook Prophet              |
| Visualization    | Power BI, Matplotlib, Seaborn |
| Environment      | Jupyter Notebook              |
| Version Control  | Git, GitHub                   |

---

## Dataset

Dataset: **RavenStack Synthetic SaaS Dataset**
Source: https://www.kaggle.com/datasets/rivalytics/saas-subscription-and-churn-analytics-dataset

---

##  Author

**Saurabh Yadav**
Aspiring Data Analyst | Python | SQL | Power BI | Machine Learning
