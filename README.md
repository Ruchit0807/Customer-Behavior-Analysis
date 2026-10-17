# Customer Shopping Behavior Analysis

An end-to-end retail analytics project exploring customer purchase patterns, product preferences, discount usage, shipping choices, and subscription behavior. The project workflow combines Python for data preparation and exploratory data analysis (EDA), PostgreSQL for business-focused SQL analysis, and Power BI for dashboard-based communication.

> **Dataset:** 3,900 purchase records and 18 original columns  
> **Primary tools:** Python, pandas, PostgreSQL, SQL, Power BI  
> **Business focus:** Customer segmentation, revenue analysis, product performance, customer retention, and marketing opportunities

## Table of Contents

- [Business Objective](#business-objective)
- [Project Workflow](#project-workflow)
- [Dataset](#dataset)
- [Analysis Questions](#analysis-questions)
- [Key Findings](#key-findings)
- [Business Recommendations](#business-recommendations)
- [Tools and Skills](#tools-and-skills)
- [Repository Structure](#repository-structure)
- [Reproducing the Analysis](#reproducing-the-analysis)
- [Limitations and Validation Notes](#limitations-and-validation-notes)
- [Author](#author)

## Business Objective

Retail teams need to understand what influences purchase value, which products attract customers, how discount and shipping choices relate to spending, and how to encourage repeat purchases. This project analyzes customer transaction and behavior data to turn descriptive data into actionable questions for marketing, merchandising, and customer-retention teams.

## Project Workflow

1. **Load and inspect data:** Read the CSV with pandas and review schema, data types, descriptive statistics, and missing values.
2. **Clean and prepare:** Handle missing review ratings, standardize column names, and check for overlapping discount/promo-code fields.
3. **Engineer features:** Create age groups and a purchase-frequency feature for further analysis.
4. **Load into PostgreSQL:** Transfer the prepared data to a relational database for SQL analysis.
5. **Analyze business questions:** Use aggregations, filtering, ranking, and customer grouping to examine revenue, products, shipping, discounts, and subscriptions.
6. **Visualize in Power BI:** Present high-level KPIs and breakdowns by customer and purchase attributes.
7. **Communicate recommendations:** Translate the analysis into ideas for retention, subscription engagement, marketing, and product positioning.

## Dataset

The source CSV contains 3,900 rows and 18 columns. The `Review Rating` field contains 37 missing values; the other columns have no missing values in the supplied file.

| Column | Description |
|---|---|
| `Customer ID` | Customer/record identifier in the supplied dataset |
| `Age` | Customer age |
| `Gender` | Customer gender |
| `Item Purchased` | Purchased product |
| `Category` | Product category |
| `Purchase Amount (USD)` | Purchase amount in USD |
| `Location` | Customer location/state |
| `Size` | Product size |
| `Color` | Product color |
| `Season` | Season associated with the purchase |
| `Review Rating` | Customer review rating |
| `Subscription Status` | Whether the customer is subscribed |
| `Shipping Type` | Shipping option selected |
| `Discount Applied` | Whether a discount was applied |
| `Promo Code Used` | Whether a promo code was used |
| `Previous Purchases` | Number of previous purchases |
| `Payment Method` | Payment method |
| `Frequency of Purchases` | Reported purchase-frequency category |

### Data preparation documented in the project

- Inspected data structure with `DataFrame.info()` and summary statistics with `DataFrame.describe()`.
- Imputed missing review ratings using the median rating within each product category.
- Standardized column names to snake case.
- Created age-group and purchase-frequency features.
- Checked whether `Discount Applied` and `Promo Code Used` were redundant; the report states that `Promo Code Used` was dropped.
- Loaded the prepared data into PostgreSQL for SQL analysis.

## Analysis Questions

The accompanying project report documents these business questions:

1. How does total revenue compare across gender groups?
2. Which customers used discounts but still spent above the average purchase amount?
3. Which products have the highest average review ratings?
4. How do average purchase amounts compare across shipping types?
5. How do subscriber and non-subscriber groups compare on customer count, average spend, and revenue?
6. Which products have the highest share of discounted purchases?
7. How are customers classified as New, Returning, or Loyal based on purchase history?
8. Which products are most frequently purchased within each category?
9. How many repeat buyers are subscribers versus non-subscribers?
10. Which age groups contribute the most revenue?

## Key Findings

The following values are calculated directly from the supplied CSV, rather than copied from potentially inconsistent presentation graphics.

- **Overall purchase value:** Total purchase amount is **$233,081**, with an average of **$59.76** per record.
- **Revenue by gender:** Records labeled Male contribute **$157,890** in purchase amount, while records labeled Female contribute **$75,191**. These totals should be interpreted in the context of the dataset's group sizes (2,652 Male records and 1,248 Female records).
- **Category contribution:** Clothing contributes **$104,264**, Accessories **$74,200**, Footwear **$36,093**, and Outerwear **$18,524** in purchase amount.
- **Shipping comparison:** Average purchase amount is approximately **$60.48 for Express** and **$58.46 for Standard** shipping, a difference of about **3.4%**.
- **Subscription comparison:** The dataset has **1,053 subscription records** and **2,847 non-subscription records**. Total purchase amount is **$62,645** for subscribers and **$170,436** for non-subscribers. Average purchase amounts are approximately **$59.49** and **$59.87**, respectively.

These are descriptive comparisons, not evidence that gender, shipping, or subscription status causes higher or lower spending.

## Business Recommendations

Based on the project questions and descriptive results, potential actions include:

- **Customer retention:** Design lifecycle messaging and loyalty benefits to encourage first-time customers to return and repeat customers to remain active.
- **Subscription engagement:** Test subscriber benefits and measure conversion, repeat purchase rate, and revenue per customer before drawing conclusions about subscription impact.
- **Discount effectiveness:** Compare discounted and non-discounted orders while tracking margin, not only purchase amount.
- **Merchandising:** Promote well-rated and frequently purchased products, while validating ratings against sample sizes.
- **Targeted marketing:** Compare age groups and customer segments using both revenue and customer counts to avoid confusing group size with customer value.
- **Shipping strategy:** Evaluate shipping preferences alongside basket size, fulfillment costs, and customer satisfaction before changing shipping offers.

## Tools and Skills

- **Python:** pandas, data inspection, missing-value treatment, feature engineering, exploratory data analysis
- **SQL / PostgreSQL:** filtering, grouping, aggregations, ranking, customer segmentation, business-question analysis
- **Power BI:** KPI cards, slicers/filters, category and age-group comparisons, dashboard storytelling
- **Analytics:** data quality checks, descriptive statistics, customer behavior analysis, insight communication, business recommendations
- **Git/GitHub:** project documentation and version-controlled portfolio presentation

## Repository Structure

```text
customer-shopping-behavior-analysis/
├── data/
│   └── customer_shopping_behavior.csv
├── reports/
│   ├── Customer_Shopping_Behavior_Analysis.pdf
│   └── Customer_Shopping_Behavior_Analysis.pptx
├── assets/
│   └── project_workflow.png
└── README.md
```

The supplied files include the dataset, report, presentation, and workflow diagram. The original Python notebook/script, PostgreSQL SQL script, and editable Power BI `.pbix` file were not included in the uploaded materials. Add those files to the repository if available so that others can reproduce the full workflow.

## Reproducing the Analysis

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis
```

### 2. Set up Python

```bash
python -m venv .venv
```

Activate the environment:

- Windows: `.venv\Scripts\activate`
- macOS/Linux: `source .venv/bin/activate`

Install the analysis dependencies:

```bash
pip install pandas numpy matplotlib seaborn jupyter sqlalchemy psycopg2-binary
```

### 3. Load the CSV

```python
import pandas as pd

df = pd.read_csv("data/customer_shopping_behavior.csv")

print(df.shape)
print(df.info())
print(df.isna().sum())
print(df.describe(include="all"))
```

### 4. Continue with the documented workflow

Use the project report as the guide for cleaning and feature engineering, load the cleaned dataset into PostgreSQL, execute SQL queries for the business questions above, and open the Power BI report if the `.pbix` file is available.

> **Reproducibility note:** The uploaded materials do not include the original Python code, SQL queries, or editable Power BI file. The command above loads and inspects the dataset; it does not by itself reproduce every reported analysis.

## Limitations and Validation Notes

- This is observational transaction data; results show associations and group differences, not causal effects.
- The dataset includes 3,900 records, but the available documentation does not establish whether each record represents a unique person or a unique order in every analysis. Interpret customer-level claims carefully.
- The accompanying presentation contains some figures that do not agree with calculations from the supplied CSV. For example, the CSV's average purchase amount is about **$60.48 for Express** and **$58.46 for Standard** shipping, not $65 and $58. Recalculate charts and narrative claims from the cleaned data before using the presentation as a source of quantitative truth.
- Customer segment percentages in the presentation should be validated against the SQL segmentation logic and underlying counts before publication.
- No profitability or margin fields are provided, so revenue/purchase amount should not be treated as profit.

## Author

**Ruchit Sonawane**

Add your GitHub profile and LinkedIn URL here before publishing.
