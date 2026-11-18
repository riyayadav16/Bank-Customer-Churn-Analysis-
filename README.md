# Bank Customer Churn Analysis

## Project Overview

Customer churn is an important challenge for banks because losing existing customers can affect revenue and long-term customer relationships.

This project analyses bank customer data to identify customer segments with the highest churn rates, understand factors associated with customer churn, and determine which key metrics retention teams should monitor.

The project uses Python for data preparation and exploratory data analysis and Power BI for business reporting and visualization.

## Business Question

**Which customer segments exhibit the highest churn risk, and which metrics should retention teams monitor?**

## Project Objectives

- Calculate the overall customer churn and retention rates.
- Identify customer segments with higher churn rates.
- Analyse churn patterns across customer demographics, geography, tenure and product holdings.
- Understand the relationship between customer activity, complaints and churn.
- Identify important KPIs for monitoring customer retention.
- Provide actionable recommendations to help banks prioritise retention efforts.

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Python | Data analysis and preparation |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Power BI | Interactive dashboard |
| DAX | KPI calculations and measures |
| Power Query | Data transformation |

## Dataset

- **Source:** Kaggle – Bank Customer Churn Records
- **Total Records:** 10,000 customers
- **Original Columns:** 18
- **Additional Columns:** 3 engineered columns

### Important Columns

| Column | Description |
|---|---|
| CreditScore | Customer's credit score |
| Geography | Customer's country |
| Gender | Customer's gender |
| Age | Customer's age |
| Tenure | Number of years with the bank |
| Balance | Customer's account balance |
| NumOfProducts | Number of products held |
| IsActiveMember | Customer activity status |
| Complain | Whether the customer raised a complaint |
| Satisfaction Score | Customer satisfaction rating |
| Exited | Customer churn status |

**Target Variable: `Exited`**

- 0 = Retained customer
- 1 = Churned customer

## Project Workflow

### 1. Data Understanding and Preparation

- Imported the dataset using Pandas.
- Examined the number of rows and columns.
- Checked data types and unique customer IDs.
- Checked missing values and duplicate records.
- Performed basic data consistency checks.
- Prepared the dataset for analysis.

### 2. Feature Engineering

Created three additional columns to make customer segmentation easier:

- **AgeGroup:** Divided customers into Young, Adult and Senior categories.
- **TenureGroup:** Grouped customers based on their relationship duration with the bank.
- **SalaryGroup:** Categorised customers into salary ranges.

### 3. Exploratory Data Analysis

Performed analysis across different customer categories:

- Overall churn and retention.
- Age-group-wise churn.
- Geography-wise churn.
- Gender-wise churn.
- Tenure-group-wise churn.
- Product-wise churn.
- Active vs inactive customers.
- Salary-group-wise churn.
- Complaint and satisfaction patterns.

### 4. Statistical Analysis

Used correlation analysis and the Chi-square test to examine relationships between selected customer attributes and churn.

This helped identify customer characteristics that have a significant association with customer churn.

### 5. Power BI Dashboard

Developed an interactive dashboard to present important business metrics and customer churn patterns.

The dashboard focuses on:

- Overall churn and retention performance.
- Customer segment-wise churn.
- Geography and demographic analysis.
- Product holdings and customer activity.
- Important metrics for retention monitoring.

## Key Findings

| Metric / Segment | Result |
|---|---:|
| Total Customers | 10,000 |
| Churned Customers | 2,038 |
| Retained Customers | 7,962 |
| Overall Churn Rate | 20.38% |
| Overall Retention Rate | 79.62% |
| Senior Customer Churn | 44.65% |
| Germany Customer Churn | 32.44% |
| Inactive Customer Churn | 26.87% |
| Active Customer Churn | 14.27% |
| Female Customer Churn | 25.07% |
| Male Customer Churn | 16.47% |

### Key Business Insights

1. **Age:** Senior customers have the highest churn rate at 44.65%, making them an important segment to investigate.

2. **Geography:** Germany has a churn rate of 32.44%, considerably higher than France and Spain.

3. **Customer Activity:** Inactive customers have a churn rate of 26.87%, compared with 14.27% among active customers.

4. **Product Holdings:** Customers holding one product have a churn rate of 27.71%, while customers holding two products have a churn rate of 7.60%.

5. **Complaints:** Customers with recorded complaints show an extremely strong association with churn. This relationship should be investigated carefully before using complaint status as a standalone retention indicator.

6. **Tenure:** New customers show a churn rate of 21.14%, compared with 19.54% among long-term customers.

## Metrics Retention Teams Should Monitor

| Metric | Why It Matters |
|---|---|
| Overall Churn Rate | Tracks the percentage of customers leaving the bank |
| Customer Retention Rate | Measures how well the bank retains customers |
| Segment-wise Churn Rate | Identifies customer groups with higher churn |
| Customer Activity Rate | Helps monitor customer engagement |
| Complaint Rate | Highlights potential customer experience issues |
| Product Holding | Helps understand the relationship between product usage and churn |
| Customer Satisfaction Score | Helps monitor customer experience |

## Business Recommendations

Based on the analysis, the bank should:

- Investigate the reasons behind higher churn among senior customers.
- Review customer experience and service issues in Germany.
- Monitor inactive customers and encourage regular engagement.
- Understand why customers holding only one product show higher churn.
- Track complaints and satisfaction levels to identify customer experience issues.
- Regularly monitor churn rates across important customer segments.

## Project Limitations

This analysis identifies customer segments and characteristics associated with higher churn rates using the available dataset.

The dataset does not contain historical customer activity records or exact churn dates. Therefore, the analysis does not establish the causes of churn or predict which individual customers will leave.

The findings represent observed patterns and associations, not proof of causation.

## Conclusion

This project provides an analytical view of bank customer churn by identifying customer segments with higher churn rates and examining important customer-related indicators.

The findings can help retention teams understand where churn is concentrated, monitor relevant business metrics and prioritise customer retention efforts.

---

**Project Type:** Data Analytics

**Technologies:** Python, Pandas, NumPy, Matplotlib, Seaborn, Power BI, DAX
