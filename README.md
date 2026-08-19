
# Customer Churn & Retention Analytics

An end-to-end **Customer Churn & Retention Analytics** project using **Python, SQLite3, Pandas, NumPy, and Power BI** to analyze customer behavior, identify high-churn segments, and quantify recurring revenue exposure.

---

## 📌 Project Overview

Customer churn is a major challenge for subscription-based businesses because losing customers directly affects recurring revenue and long-term growth.

This project analyzes **5,021 customer records** to understand churn patterns across different customer segments. Customer, subscription, and support data are processed using **Python and SQLite3**, followed by exploratory data analysis and an interactive **Power BI dashboard**.

The analysis identifies high-risk customer segments, calculates important churn KPIs, measures revenue at risk, and provides data-driven recommendations for improving customer retention.

---

## 🎯 Objectives

* Analyze overall customer churn and retention
* Identify customer segments with higher churn rates
* Compare churn across plan and contract types
* Analyze revenue associated with churned customers
* Build an interactive Power BI dashboard
* Create reusable DAX measures for churn KPIs
* Provide actionable customer retention recommendations

---

## 🛠️ Tech Stack

| Technology     | Usage                                |
| -------------- | ------------------------------------ |
| **Python**     | Data processing and analysis         |
| **Pandas**     | Data cleaning and transformation     |
| **NumPy**      | Numerical analysis                   |
| **Matplotlib** | Data visualization                   |
| **Seaborn**    | Exploratory visualization            |
| **SQLite3**    | Database storage and SQL queries     |
| **Power BI**   | Interactive dashboard                |
| **DAX**        | KPI and business metric calculations |

---

## 🔄 Data Analytics Workflow

```text
SQLite3 Database
       ↓
Data Extraction
       ↓
Python + Pandas
       ↓
Data Cleaning
       ↓
Feature Engineering
       ↓
Exploratory Data Analysis
       ↓
Power BI Data Model
       ↓
DAX Measures
       ↓
Interactive Dashboard
       ↓
Business Insights
       ↓
Retention Recommendations
```

---

## 📊 Key Results

The analysis of **5,021 customers** produced the following results:

| Metric                          |                   Result |
| ------------------------------- | -----------------------: |
| **Total Customers**             |                    5,021 |
| **Churned Customers**           |                    1,540 |
| **Active Customers**            |                    3,481 |
| **Churn Rate**                  |                   30.67% |
| **Retention Rate**              |                   69.33% |
| **Monthly Revenue at Risk**     |                  ₹77,089 |
| **Annualized Revenue Exposure** | Approximately ₹9.25 lakh |

### Plan-Level Findings

| Plan Type    | Churn Rate |
| ------------ | ---------: |
| **Basic**    | **31.81%** |
| **Standard** |     30.48% |
| **Premium**  |     29.77% |

The **Basic plan has the highest churn rate at 31.81%**, making it an important segment for targeted retention strategies.

Monthly-contract customers also demonstrate greater churn instability compared with annual-contract customers.

---

## 📈 Power BI Dashboard

The Power BI dashboard provides an interactive view of customer churn and retention performance.

### KPI Cards

* Total Customers
* Churned Customers
* Churn Rate
* Retention Rate
* Revenue at Risk
* Average Churn Score, where applicable

### Dashboard Analysis

* Churn Rate by Plan Type
* Churn Rate by Contract Type
* Revenue at Risk
* Geographic Churn Analysis
* Customer Segmentation
* Interactive filters for customer attributes

### Dashboard Preview

Add your Power BI dashboard screenshot here:

```markdown
![Customer Churn Power BI Dashboard](screenshots/dashboard.png)
```

---

## 🧮 Important DAX Measures

### Total Customers

```dax
Total Customers =
COUNTROWS(Sheet1)
```

### Churned Customers

```dax
Churned Customers =
CALCULATE(
    COUNTROWS(Sheet1),
    Sheet1[churn_flag] = 1
)
```

### Churn Rate

```dax
Churn Rate =
DIVIDE(
    [Churned Customers],
    [Total Customers],
    0
)
```

### Retention Rate

```dax
Retention Rate =
DIVIDE(
    [Total Customers] - [Churned Customers],
    [Total Customers],
    0
)
```

### Revenue at Risk

```dax
Revenue at Risk =
CALCULATE(
    SUM(Sheet1[monthly_charges]),
    Sheet1[churn_flag] = 1
)
```

---

## 💡 Business Insights

The analysis provides several actionable insights:

1. **Basic-plan customers have the highest churn rate**, suggesting the need for targeted retention campaigns.

2. **Monthly-contract customers show greater churn instability**, indicating that longer-term contracts may provide greater customer stability.

3. **Revenue at Risk** helps quantify the financial impact of customer churn instead of focusing only on customer counts.

4. Combining **churn rate with revenue exposure** can help businesses prioritize retention efforts more effectively.

---

## 🎯 Business Recommendations

Based on the analysis, businesses can:

* Focus retention campaigns on Basic-plan customers
* Target monthly-contract customers with retention offers
* Monitor revenue at risk by customer segment
* Investigate price-related cancellation patterns
* Analyze support interactions associated with churn
* Use Power BI to continuously monitor churn KPIs

---

## 🚀 Future Scope

The project can be extended with:

* Machine Learning-based churn prediction
* Customer Lifetime Value (CLV) analysis
* Automated high-risk customer alerts
* Real-time churn monitoring
* Advanced customer segmentation
* CRM integration
* Automated retention workflows

---

## 📁 Repository Structure

```text
customer-churn-retention-analytics/
│
├── data/
│   └── customer_churn.db
│
├── python/
│   ├── data_cleaning.py
│   ├── eda.py
│   └── feature_engineering.py
│
├── sql/
│   └── analysis_queries.sql
│
├── powerbi/
│   └── customer_churn_dashboard.pbix
│
├── screenshots/
│   └── dashboard.png
│
├── reports/
│   └── Customer_Churn_Analytics_Report.pdf
│
├── requirements.txt
└── README.md
```

---

## 📋 Data Sources

The project uses three primary SQLite tables:

* **Customers** — Customer profile and demographic information
* **Subscriptions** — Plan, contract, subscription, and billing information
* **Support** — Customer support interaction and issue information

These tables are combined to create the final analytical dataset.

---

## 🔍 Key Analytical Fields

| Field               | Description                                                 |
| ------------------- | ----------------------------------------------------------- |
| `customer_id`       | Unique customer identifier                                  |
| `plan_type`         | Customer subscription plan                                  |
| `contract_type`     | Type of customer contract                                   |
| `monthly_charges`   | Monthly recurring customer charge                           |
| `cancellation_date` | Customer cancellation date                                  |
| `churn_flag`        | `1` = Churned, `0` = Active                                 |
| `churn_score`       | Churn-related risk/score field, depending on implementation |

---

## 💻 Requirements

### Software

* Python 3.x
* SQLite3
* Power BI Desktop

### Python Libraries

```text
pandas
numpy
matplotlib
seaborn
```

Install the Python dependencies using:

```bash
pip install pandas numpy matplotlib seaborn
```

## 🔄 Analytics Workflow

```text
┌────────────────────┐
│  SQLite3 Database  │ ──┐
└────────────────────┘   │ (Data Extraction)
                         ▼
             ┌───────────────────────┐
             │  Python ETL Pipeline  │ (Pandas & NumPy Data Cleaning)
             └───────────────────────┘
                         │
                         ▼
             ┌───────────────────────┐
             │ Feature Engineering & │ (Interaction Flags & Tenure Buckets)
             │   Exploratory Analysis│
             └───────────────────────┘
                         │
                         ▼
             ┌───────────────────────┐
             │   Power BI Data Model │ (Star-Schema & Relationship Mapping)
             └───────────────────────┘
                         │
                         ▼
             ┌───────────────────────┐
             │  DAX Metric Modeling  │ (Dynamic KPI Formulation)
             └───────────────────────┘
                         │
                         ▼
             ┌───────────────────────┐
             │ Business Insights &   │ (Targeted Retention Recommendations)
             │  Strategic Roadmap    │
             └───────────────────────┘

## 🎓 Project Type

**Academic / Portfolio Data Analytics Project**

This project demonstrates an end-to-end analytics workflow covering:

**SQL → Python → Data Cleaning → EDA → Feature Engineering → Power BI → DAX → Business Insights**

---

## 👨‍💻 Author

**CHINMAY S. KULKARNI**

**B.Tech Information Technology**


**Academic Year: 2026–2027**
