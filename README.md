<div align="center">

# 🛍️ Customer Shopping Behavior Analysis
### From 3,900 shopping records to actionable retail insights

**An end-to-end Data Analytics portfolio project using Python, PostgreSQL & Power BI**

![Python](https://img.shields.io/badge/Python-Data%20Cleaning-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-SQL%20Analysis-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Interactive%20Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/Project-Portfolio-2E8B57?style=for-the-badge)

**[Explore the Dataset](#-dataset-at-a-glance) · [Discover Insights](#-key-findings) · [View Dashboard](#-power-bi-dashboard) · [Read Report](reports/Customer_Shopping_Behavior_Analysis.pdf)**

</div>

---

## ✨ The Story Behind the Data

**What makes customers spend more? Which products drive revenue? Do subscriptions and discounts actually influence purchasing behavior?**

This project investigates retail shopping patterns across **3,900 purchase records** to answer practical questions that a marketing, merchandising, or business intelligence team might ask. The workflow follows the analytics lifecycle: **raw data → cleaning & EDA → PostgreSQL analysis → Power BI dashboard → business recommendations**.

> 🎯 **Goal:** Turn transaction-level data into clear insights about revenue, customer behavior, product performance, and retention opportunities.

## 📌 Project at a Glance

| 🧾 Purchase Records | 🧩 Original Features | 🧹 Missing Ratings | 💵 Average Purchase |
|:---:|:---:|:---:|:---:|
| **3,900** | **18** | **37** | **$59.76** |

**Domain:** Retail / E-commerce Analytics  
**Core skills:** Data Cleaning · Exploratory Data Analysis · SQL Aggregation · Customer Segmentation · KPI Reporting · Data Visualization · Business Storytelling

## 🗺️ End-to-End Workflow

![Project workflow](assets/project_workflow.png)

| Stage | What happens | Tool |
|---|---|---|
| **01 · Define** | Frame business questions around customers, products, and revenue | Business analysis |
| **02 · Prepare** | Inspect records, address missing ratings, standardize fields, engineer features | Python / pandas |
| **03 · Investigate** | Answer ten business questions using structured queries | PostgreSQL / SQL |
| **04 · Visualize** | Build an interactive overview of key retail metrics | Power BI |
| **05 · Recommend** | Translate findings into marketing and retention opportunities | Reporting |
| **06 · Present** | Share findings in a report and presentation | PDF / PowerPoint |

## 🧩 Business Questions

The analysis is organized around four decisions:

| Business area | Questions explored |
|---|---|
| 💰 **Revenue** | Which gender and age groups contribute most to total purchase amount? |
| 🛒 **Products** | Which products sell most, rate highest, or depend most on discounts? |
| 🚚 **Purchase behavior** | How do shipping preferences and discount usage relate to purchase value? |
| 💜 **Retention** | How do subscription status, previous purchases, and customer segments relate? |

The accompanying [project report](reports/Customer_Shopping_Behavior_Analysis.pdf) documents **10 SQL business analyses**, including revenue by gender, high-value discount users, top-rated products, shipping comparisons, subscription comparisons, discount-dependent products, customer segmentation, top products per category, repeat buyers, and revenue by age group.

## 📂 Dataset at a Glance

The source file is [`data/customer_shopping_behavior.csv`](data/customer_shopping_behavior.csv).

| Feature group | Included fields |
|---|---|
| Customer profile | Customer ID, Age, Gender, Location |
| Shopping details | Item Purchased, Category, Purchase Amount (USD), Size, Color, Season |
| Engagement | Review Rating, Subscription Status, Previous Purchases, Frequency of Purchases |
| Transaction preferences | Shipping Type, Discount Applied, Promo Code Used, Payment Method |

### 🧼 Cleaning and Feature Engineering

The project report documents the following steps:

- Loaded the CSV using **pandas** and inspected the structure using `.info()` and `.describe()`.
- Addressed **37 missing values in `Review Rating`** using the **median rating by product category**.
- Standardized column names into **snake_case**.
- Created `age_group` and `purchase_frequency_days` features.
- Checked redundancy between `discount_applied` and `promo_code_used`, and removed the latter in the documented cleaned dataset.
- Loaded prepared data into **PostgreSQL** for business analysis.

## 🔎 Key Findings

The figures below are computed from the supplied raw CSV. They are descriptive results, not causal claims.

### 💵 1. Purchase value

- **Total purchase amount:** **$233,081**
- **Average purchase amount:** **$59.76**

### 🧥 2. Revenue by product category

| Category | Purchase amount |
|---|---:|
| 🥇 Clothing | **$104,264** |
| 🥈 Accessories | **$74,200** |
| 🥉 Footwear | **$36,093** |
| Outerwear | **$18,524** |

**Takeaway:** Clothing is the largest revenue-contributing category in this dataset, making it an important area for merchandising analysis.

### 🚚 3. Shipping preference vs. basket value

| Shipping type | Average purchase amount |
|---|---:|
| Express | **$60.48** |
| Standard | **$58.46** |

**Takeaway:** Express-shipping records have approximately **3.4% higher average purchase amounts** than Standard-shipping records. This association does not establish that Express shipping causes larger purchases.

### 💜 4. Subscription comparison

| Metric | Subscribed | Not subscribed |
|---|---:|---:|
| Records | **1,053** | **2,847** |
| Total purchase amount | **$62,645** | **$170,436** |
| Average purchase amount | **$59.49** | **$59.87** |

**Takeaway:** Non-subscribers account for more total purchase amount primarily because there are more non-subscriber records. Average purchase amounts are very similar across the two groups.

### 👥 5. Revenue by gender

| Gender | Records | Total purchase amount |
|---|---:|---:|
| Male | **2,652** | **$157,890** |
| Female | **1,248** | **$75,191** |

**Takeaway:** Compare both totals and group sizes when interpreting revenue differences; a larger group can contribute more total revenue without spending more per transaction.

## 📊 Power BI Dashboard

The project report includes a Power BI dashboard designed to bring the analysis together in one view.

**Featured KPI cards**
- Customer/record count
- Average purchase amount
- Average review rating

**Interactive breakdowns**
- Subscription-status distribution
- Revenue and sales by category
- Revenue and sales by age group
- Filters for gender, category, subscription status, and shipping type

📄 **[View dashboard in the project report (page 7)](reports/Customer_Shopping_Behavior_Analysis.pdf)**

> 📸 **Portfolio enhancement:** Add an exported dashboard screenshot to `assets/dashboard.png` and the editable `.pbix` file to a `powerbi/` folder when available. These assets were not included in the uploaded materials.

## 💡 Business Recommendations

| Opportunity | Recommended next step | KPI to monitor |
|---|---|---|
| 🎁 **Customer loyalty** | Test repeat-purchase rewards and lifecycle messaging | Repeat purchase rate |
| 💌 **Subscription engagement** | Experiment with member-exclusive benefits | Subscription conversion |
| 🏷️ **Discount optimization** | Assess discount effectiveness alongside margins | Contribution margin |
| ⭐ **Product positioning** | Feature well-rated and frequently purchased items | Product conversion |
| 🎯 **Targeted marketing** | Compare age and behavioral segments before tailoring campaigns | Revenue per customer |

These are **proposed actions**, not measured outcomes from implemented campaigns.

## 🧰 Tech Stack

| Technology | Role |
|---|---|
| **Python / pandas** | Loading, data quality checks, cleaning, feature engineering, EDA |
| **PostgreSQL / SQL** | Business queries, aggregation, filtering, ranking, segmentation |
| **Power BI** | KPI visualization, interactive filtering, dashboard reporting |
| **PowerPoint / PDF** | Stakeholder-facing presentation and project documentation |

## 📁 Repository Structure

```text
customer-shopping-behavior-analysis/
├── README.md
├── data/
│   └── customer_shopping_behavior.csv
├── reports/
│   ├── Customer_Shopping_Behavior_Analysis.pdf
│   └── Customer_Shopping_Behavior_Analysis.pptx
└── assets/
    └── project_workflow.png
```

**Recommended additions** (not part of the currently supplied files):

```text
├── notebooks/
│   └── customer_shopping_eda.ipynb
├── sql/
│   └── business_analysis.sql
└── powerbi/
    └── customer_behavior_dashboard.pbix
```

## 🚀 Explore the Project Locally

**1. Clone your repository** (replace the placeholder with your GitHub username):

```bash
git clone https://github.com/YOUR_USERNAME/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis
```

**2. Install pandas:**

```bash
pip install pandas
```

**3. Inspect the source data:**

```python
import pandas as pd

df = pd.read_csv("data/customer_shopping_behavior.csv")

print("Shape:", df.shape)
print("\nMissing values:\n", df.isna().sum())
print("\nSummary:\n", df.describe(include="all"))
```

**4. Explore the supporting deliverables:**

- [Project report (PDF)](reports/Customer_Shopping_Behavior_Analysis.pdf)
- [Presentation (PowerPoint)](reports/Customer_Shopping_Behavior_Analysis.pptx)
- [Workflow diagram](assets/project_workflow.png)

> **Reproducibility:** The original Python notebook/script, SQL queries, and Power BI `.pbix` were not provided. The steps above reproduce initial data inspection, not the complete documented pipeline.

## ⚠️ Interpretation & Quality Notes

- The presentation and report include **some inconsistent figures**. This README prioritizes values calculated from the provided raw CSV; verify the cleaned dataset and refresh any visuals before publication.
- In particular, presentation claims about **shipping uplift, gender revenue, subscription impact, and customer-segment percentages** should not be reused without checking the underlying calculations.
- The dataset does not establish a complete time-series of repeat orders per identified customer, so avoid interpreting segmentation labels as verified retention outcomes without reviewing the SQL logic.
- Revenue/purchase amount is **not profit**; margins and fulfillment costs are not available.
- Differences across customer groups are descriptive and should not be interpreted as proof of causation.

## 📚 Project Deliverables

| Resource | Link |
|---|---|
| 🗃️ Raw dataset | [CSV](data/customer_shopping_behavior.csv) |
| 📑 Detailed analysis | [PDF report](reports/Customer_Shopping_Behavior_Analysis.pdf) |
| 🎤 Stakeholder presentation | [PowerPoint](reports/Customer_Shopping_Behavior_Analysis.pptx) |
| 🧭 Process overview | [Workflow image](assets/project_workflow.png) |

---

<div align="center">

### 👨‍💻 About the Author

**Ruchit Sonawane**

*Data Analytics · SQL · Python · Power BI · Business Insights*

**If this project helped you, consider giving the repository a ⭐!**

</div>
