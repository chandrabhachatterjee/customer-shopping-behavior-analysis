# Customer Shopping Behavior Analysis

**An end-to-end customer analytics project using Python, Pandas, PostgreSQL, SQL, and Power BI.**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=databricks&logoColor=white)

## 📌 Project Overview

This project analyzes customer shopping behavior using Python, Pandas, PostgreSQL, SQL, and Power BI. It follows an end-to-end data analytics workflow, starting with data exploration and cleaning, continuing through database integration and SQL analysis, and ending with interactive business reporting.

The dataset contains **3,900 customer records and 18 original columns**. The analysis focuses on customer spending, product ratings, discount usage, shipping preferences, subscription status, customer segmentation, and revenue distribution.

The primary objective is to transform raw customer data into structured insights that can help businesses better understand purchasing patterns and customer behavior.

## 🎯 Project Objectives

- Clean and prepare customer shopping data using Python and Pandas.
- Handle missing values and improve data quality.
- Perform feature engineering to create additional analytical attributes.
- Store the processed dataset in PostgreSQL.
- Write SQL queries to investigate business questions.
- Analyze customer segments, spending patterns, and discount usage.
- Build a Power BI dashboard for visual reporting.
- Demonstrate an end-to-end data analytics workflow.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Data preparation and transformation |
| Pandas | Data cleaning, exploration, and feature engineering |
| Jupyter Notebook | Interactive analysis and documentation |
| PostgreSQL | Relational database storage |
| SQL | Business analysis and querying |
| SQLAlchemy | Python-to-PostgreSQL connectivity |
| psycopg2 | PostgreSQL database driver |
| Power BI | Dashboard development and visual reporting |

## 🔄 Project Workflow

```text
Customer Shopping Dataset (CSV)
              |
              v
       Python + Pandas
              |
              v
     Data Cleaning and
    Feature Engineering
              |
              v
       PostgreSQL Table
              |
              v
       SQL Analysis
              |
              v
       Power BI Dashboard
              |
              v
     Business Insights
```

## 📊 Dataset Description

The original dataset contains **3,900 records and 18 columns**, covering customer demographics, purchases, product categories, ratings, discounts, shipping, payment methods, subscription status, and purchase frequency.

Important fields include:

- `customer_id`
- `age`
- `gender`
- `item_purchased`
- `category`
- `purchase_amount`
- `review_rating`
- `subscription_status`
- `shipping_type`
- `discount_applied`
- `previous_purchases`
- `frequency_of_purchases`

*Note: Include the original CSV in the repository only if you have permission to redistribute it. Document the dataset's original source where available.*

## 🧹 Data Cleaning and Feature Engineering

The Jupyter Notebook performs the following operations using Pandas:

1. **Data exploration:** Examines sample records, data types, descriptive statistics, and missing values.
2. **Missing-value treatment:** Fills missing review ratings using the median rating within the corresponding product category. The original dataset contains 37 missing review ratings.
3. **Column standardization:** Converts column names to lowercase, replaces spaces with underscores, and standardizes the purchase amount field to `purchase_amount`.
4. **Age-group creation:** Uses `pandas.qcut()` to divide customers into four quantile-based age groups: Young Adult, Adult, Middle-aged, and Senior.
5. **Purchase-frequency conversion:** Converts purchase-frequency labels into approximate day intervals in a new `purchase_frequency_days` column.
6. **Redundant-column validation:** Checks whether `discount_applied` and `promo_code_used` contain identical values before dropping the redundant field.

These steps prepare the data for consistent database storage and downstream analysis.

## 🗄️ PostgreSQL Database Integration

After data cleaning and transformation, the processed DataFrame is loaded into PostgreSQL using SQLAlchemy.

**Database:** `customer_behaviour`  
**Table:** `customer`

This integration allows SQL queries to operate on the prepared dataset and supports a structured workflow between Python-based data preparation and database analysis.

> Before running the notebook, configure your PostgreSQL connection for your own environment. Avoid committing passwords, credentials, or other sensitive configuration details to GitHub.

## 🔍 SQL Analysis

The SQL script contains **10 business-oriented analytical queries**.

| No. | Business Question | SQL Concepts |
|---:|---|---|
| 1 | What is the total purchase revenue by gender? | `SUM()`, `GROUP BY` |
| 2 | Which discounted purchases meet or exceed the overall average purchase amount? | `WHERE`, subquery, `AVG()` |
| 3 | Which five products have the highest average review ratings? | `AVG()`, `ROUND()`, `ORDER BY`, `LIMIT` |
| 4 | How do average purchase amounts compare for Standard and Express shipping? | Filtering, `AVG()`, `GROUP BY` |
| 5 | How do customer count, average spend, and total revenue compare by subscription status? | `COUNT()`, `AVG()`, `SUM()` |
| 6 | Which five products have the highest discount-use percentages? | `CASE WHEN`, conditional aggregation |
| 7 | How many customers fall into New, Returning, and Loyal segments? | CTE, `CASE WHEN`, `COUNT()` |
| 8 | What are the top three products within each category by record frequency? | CTE, `ROW_NUMBER()`, `PARTITION BY` |
| 9 | How are customers with more than five previous purchases distributed by subscription status? | `WHERE`, `GROUP BY`, `COUNT()` |
| 10 | What is the total revenue by age group? | `SUM()`, `GROUP BY`, `ORDER BY` |

### SQL Skills Demonstrated

- Aggregate functions: `SUM()`, `AVG()`, and `COUNT()`
- Filtering and sorting
- Grouping and conditional aggregation
- `CASE WHEN` statements
- Subqueries
- Common Table Expressions (CTEs)
- Window functions
- `ROW_NUMBER()` and `PARTITION BY`
- Percentage calculations and rounding
- Customer segmentation

## 📈 Power BI Dashboard

The project includes a Power BI report file:

**Dashboard file:** `customer_behave.pbix`

The dashboard complements the Python and SQL analysis by providing a visual reporting layer for exploring customer shopping data.

### How to View the Dashboard

1. Clone or download this repository.
2. Install or open **Microsoft Power BI Desktop**.
3. Open `customer_behave.pbix`.
4. If prompted, configure the required data source and database connection.
5. Refresh the data if necessary to review the report.

To improve the GitHub presentation, add a screenshot of the dashboard to the `screenshots/` folder and embed it below:

```markdown
![Customer Shopping Behavior Dashboard](screenshots/dashboard-overview.png)
```

*The screenshot will appear on GitHub after you add the image at the specified path. The `.pbix` file itself can be opened in Power BI Desktop.*

## 📁 Repository Structure

Organize the repository as follows:

```text
customer-shopping-behavior-analysis/
│
├── customer_shopping_behavior_analysis.ipynb
├── customer_shopping_analysis.sql
├── customer_behave.pbix
├── customer_shopping_behavior.csv
├── screenshots/
│   └── dashboard-overview.png
└── README.md
```

**Important:** The filenames above are recommended names. Rename your existing notebook and SQL script to match them, or update the README to reflect your actual filenames. Include the CSV and dashboard screenshot only when available and appropriate to share.

## 💡 Business Applications

The analysis can help explore:

- Differences in recorded purchase revenue across customer groups.
- Products with high average review ratings.
- Product-level discount usage.
- Spending patterns by subscription status.
- Customer segmentation based on previous purchases.
- Popular products within individual categories.
- Revenue distribution across age groups.
- Differences in average purchase amounts by shipping type.

These are potential analytical applications. Specific business conclusions should be based on the actual SQL outputs and verified Power BI dashboard metrics.

## ⚠️ Limitations

- The analysis is descriptive and does not establish causal relationships between discounts, subscriptions, shipping methods, and spending.
- Age groups are based on dataset quantiles rather than fixed, standard age ranges.
- Purchase-frequency day values are approximations.
- Customer-segmentation rules should be reviewed for zero or missing previous-purchase values.
- Revenue comparisons should be considered alongside customer counts and average spending.
- The current SQL queries do not assess profitability, customer lifetime value, or time-based retention.

## 🚀 Future Enhancements

- Add dashboard screenshots and document the exact KPIs and visual interactions.
- Include product costs, profit margins, and profitability analysis.
- Add time-based trends and cohort analysis if transaction dates become available.
- Create reusable SQL views for key metrics.
- Introduce automated data-quality checks.
- Improve database loading with explicit schemas and incremental processing.
- Extend the dashboard with additional verified metrics and drill-through analysis.
- Add customer retention and lifetime-value analysis when the necessary data is available.

## 🏁 Conclusion

The Customer Shopping Behavior Analysis project brings together Python-based data preparation, PostgreSQL database integration, SQL analytics, and Power BI reporting in a practical analytics workflow.

It demonstrates hands-on skills in data cleaning, feature engineering, relational querying, customer segmentation, product ranking, and business-focused reporting.

## 👨‍💻 Author

**Chandrabha Chatterjee**

*Data Analytics | Python | Pandas | SQL | PostgreSQL | Power BI*

---

If you have suggestions for improving the analysis or dashboard, feel free to open an issue or share feedback
