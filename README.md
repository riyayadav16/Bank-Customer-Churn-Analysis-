# Bank Customer Churn & Retention Analysis

## Project Overview
Customer churn directly erodes a bank's deposit base and increases acquisition costs. Across this portfolio of **10,000 bank customers**, **2,038 customers exited (20.38% churn rate)**, resulting in **$186M in lost balances**.

This end-to-end data analytics project uses **Python** for data preparation, exploratory data analysis (EDA), and statistical testing, and **Power BI (DAX & Power Query)** for executive reporting. It isolates the highest-risk customer segments, separates actionable leading indicators from lagging signals, and translates findings into prioritized, revenue-backed retention strategies.

## Business Question
**Which customer segments exhibit the highest churn and deposit-loss risk, and which metrics and actions should retention teams prioritize?**

## Project Objectives
- Quantify overall customer churn, retention rates, and total deposit balances at risk.
- Identify high-risk customer segments across demographics, geography, tenure, and product holdings.
- Distinguish actionable leading indicators (e.g., customer inactivity) from lagging signals (e.g., complaints).
- Validate statistically significant churn drivers using correlation analysis and Chi-square testing.
- Define core KPIs for ongoing retention monitoring and deliver prioritized business recommendations.

---

## Tools & Technologies

| Tool | Purpose |
| :--- | :--- |
| **Python** | Data analysis, cleaning, and preparation |
| **Pandas** | Data manipulation and feature engineering |
| **NumPy** | Numerical operations |
| **Matplotlib & Seaborn** | Exploratory and statistical data visualization |
| **Power BI** | Interactive executive dashboard and Key Influencers analysis |
| **DAX** | Custom KPI measures, financial risk calculations, and dynamic data labels |
| **Power Query** | Data transformation and categorical binning |

---

## Dataset
- **Source:** Kaggle – Bank Customer Churn Records
- **Total Records:** 10,000 customers
- **Original Columns:** 18
- **Engineered Columns:** 3 (`AgeGroup`, `TenureGroup`, `SalaryGroup`) + Power BI segmentation columns (`Activity Status`, `Risk Tier`)
- **Target Variable:** `Exited` (`0` = Retained customer, `1` = Churned customer)

### Important Columns

| Column | Description |
| :--- | :--- |
| `CreditScore` | Customer's credit score |
| `Geography` | Customer's country (France, Germany, Spain) |
| `Gender` | Customer's gender |
| `Age` | Customer's age |
| `Tenure` | Number of years with the bank |
| `Balance` | Customer's account balance |
| `NumOfProducts` | Number of bank products held |
| `IsActiveMember` | Customer activity status (`1` = Active, `0` = Inactive) |
| `Complain` | Whether the customer raised a complaint (`1` = Yes, `0` = No) |
| `Satisfaction Score` | Customer satisfaction rating |
| `Exited` | Customer churn status (`1` = Churned, `0` = Retained) |

---

## Project Workflow

### 1. Data Understanding & Preparation
- Imported the dataset using Pandas and inspected schema, data types, and unique customer IDs.
- Checked for missing values, duplicate records, and data consistency issues.

### 2. Feature Engineering
Created additional columns to enable clear business segmentation:
- `AgeGroup`: Divided customers into **Young (<30)**, **Adult (30–50)**, and **Senior (50+)**.
- `TenureGroup`: Grouped customers based on relationship duration with the bank.
- `SalaryGroup`: Categorized customers into estimated salary ranges.
- `Activity Status` & `Risk Tier`: Built in Power BI/DAX to flag disengagement and high-value accounts at risk.

### 3. Exploratory Data Analysis (EDA)
Analyzed churn patterns across overall retention, age groups, geography, gender, tenure, product holdings, activity status, salary brackets, and complaint/satisfaction records.

### 4. Statistical Analysis
Applied **correlation analysis** and **Chi-square tests** to verify which customer attributes have statistically significant associations with churn.

### 5. Power BI Executive Dashboard
Built an interactive report structured around executive decision-making:
- Top-level KPI cards reconciling customer counts and lost deposit balances.
- Regional rate-vs.-volume breakdown, demographic risk matrix, product-tier churn with dynamic sample sizes (`n=`), and Key Influencers analysis.
- Prioritized recommendations panel backed by deposit-protection estimates.

---

## Key Findings

| Metric / Segment | Result |
| :--- | :--- |
| **Total Customers** | 10,000 |
| **Churned Customers** | 2,038 |
| **Retained Customers** | 7,962 |
| **Overall Churn Rate** | 20.38% |
| **Overall Retention Rate** | 79.62% |
| **Total Lost Balance** | $186M |
| **Germany Customer Churn** | 32.44% |
| **Senior Customer Churn (50+)** | 44.65% |
| **German Senior Churn (Peak Segment)** | 59.80% |
| **Inactive Customer Churn** | 26.87% |
| **Active Customer Churn** | 14.27% |
| **Female Customer Churn** | 25.07% |
| **Male Customer Churn** | 16.47% |

---

## Key Business Insights

1. **Geography (Rate vs. Volume):** Germany drives the highest churn risk at **32.44%**—double the rate of France and Spain. Although Germany (814 exits) and France (811 exits) lost nearly identical customer volumes, Germany's smaller customer base makes it the primary risk driver, accounting for over half of total lost deposits.
2. **Age:** Senior customers (50+) churn at **44.65%** overall, with **German Seniors peaking at 59.8%**.
3. **Customer Activity:** Inactive customers churn at **26.87%**, nearly **2x** the rate of active customers (**14.27%**), making disengagement a strong leading indicator.
4. **Product Holdings:** Customers holding **2 products** are the most loyal (**7.60% churn, n=4,590**), compared to 1-product holders (**27.71%**). Churn spikes sharply at **3 products (82.7%, n=266)** and **4 products (100%, n=60)**, indicating potential fee or onboarding friction (annotated with sample sizes for statistical transparency).
5. **Tenure:** Newer customers exhibit slightly higher churn (**21.14%**) compared to long-term customers (**19.54%**).
6. **Complaints (Data Leakage Warning):** Customers with recorded complaints show a **99.51%** association with churn. Because customers typically file complaints *as* they close accounts, this variable behaves as a **lagging signal (data leakage)** rather than a predictive root cause and is intentionally excluded from primary churn-driver visuals.

---

## Analytical Rigor & Data Integrity
- **Eliminating Data Leakage:** Replaced `Complain` in the executive dashboard with `Activity Status` so stakeholders focus on actionable leading indicators.
- **Sample Size Transparency:** Added dynamic `n=` counts to product-tier visuals so extreme percentages (e.g., 100% churn on 4 products) are evaluated alongside their small sample size (`n=60`).
- **Financial Reconciliation:** All KPIs and risk tiers reconcile cleanly across the full 10,000-customer base (`7,962 + 2,038 = 10,000`).

---

## Metrics Retention Teams Should Monitor

| Metric | Why It Matters |
| :--- | :--- |
| **Overall Churn & Retention Rate** | Tracks portfolio-level customer loss and retention health |
| **Churned Balance & Balance at Risk** | Quantifies financial impact in dollars rather than headcount alone |
| **Segment-Wise Churn Rate** | Pinpoints high-risk cohorts (e.g., Germany, Seniors, 3–4 product holders) |
| **Customer Activity Rate** | Serves as an early-warning indicator of disengagement before exit |
| **Product Penetration (1 vs. 2+ Products)** | Tracks progress toward the 2-product loyalty sweet spot |
| **Complaint Rate & Satisfaction Score** | Monitors customer experience friction as lagging service health indicators |

---

## Prioritized Business Recommendations

| Priority | Action | Business Rationale & Estimated Impact |
| :--- | :--- | :--- |
| **1. Top Priority (Strategic)** | **Audit Germany Operations** | Germany drives 32.44% churn—2x France and Spain—and over half of lost deposits. Reducing German churn by 10% protects **~$9.8M** in balances. |
| **2. Early Warning** | **Trigger Inactivity Alerts** | Inactive members churn at nearly 2x the rate of active ones, with German Seniors peaking at 59.8%. Launch automated re-engagement campaigns at 30–60 days of dormancy. |
| **3. Product Strategy** | **Optimize Around 2 Products** | Cross-sell 1-product holders into a 2nd product (7.60% churn), and audit fees/onboarding for 3–4 product holders where churn spikes to 83–100% (`n=326`). |
| **4. Quick Win (Immediate)** | **Protect High-Risk Retained Accounts** | Assign relationship managers to the **25 retained high-risk, high-value accounts ($3.01M balance)** this week for proactive retention outreach. |

---

## DAX Formulas Used in Power BI

### Core KPI Measures
```dax
Total Customers = 
COUNTROWS('BankCustomers')

Churned Customers = 
CALCULATE(
    COUNTROWS('BankCustomers'),
    'BankCustomers'[Exited] = 1
)

Retained Customers = 
CALCULATE(
    COUNTROWS('BankCustomers'),
    'BankCustomers'[Exited] = 0
)

Churn Rate % = 
DIVIDE([Churned Customers], [Total Customers], 0)
```

### Financial & Risk Measures
```dax
Total Balance = 
SUM('BankCustomers'[Balance])

Churned Balance = 
CALCULATE(
    SUM('BankCustomers'[Balance]),
    'BankCustomers'[Exited] = 1
)

Retained Balance = 
CALCULATE(
    SUM('BankCustomers'[Balance]),
    'BankCustomers'[Exited] = 0
)

High-Value Retained Balance at Risk = 
CALCULATE(
    SUM('BankCustomers'[Balance]),
    'BankCustomers'[Exited] = 0,
    'BankCustomers'[Risk Tier] = "High Risk",
    'BankCustomers'[Balance] >= 100000
)
```

### Dynamic Data Labels
```dax
Sample Size Label = 
"(n=" & FORMAT([Total Customers], "#,##0") & ")"

Exits Label = 
FORMAT([Churned Customers], "#,##0") & " exits"
```

### Calculated Columns (Segmentation)
```dax
Customer Status = 
IF('BankCustomers'[Exited] = 1, "Churned", "Retained")

Activity Status = 
IF('BankCustomers'[IsActiveMember] = 1, "Active Member", "Inactive Member")

Age Group = 
SWITCH(
    TRUE(),
    'BankCustomers'[Age] < 30, "Young (<30)",
    'BankCustomers'[Age] <= 50, "Adult (30-50)",
    "Senior (50+)"
)

Risk Tier = 
SWITCH(
    TRUE(),
    'BankCustomers'[Age] > 50 && 'BankCustomers'[IsActiveMember] = 0 && 'BankCustomers'[Geography] = "Germany", "High Risk",
    'BankCustomers'[NumOfProducts] >= 3, "High Risk",
    'BankCustomers'[Age] > 50 || 'BankCustomers'[IsActiveMember] = 0, "Medium Risk",
    "Low Risk"
)
```

---

## Definitions & Assumptions
- **Currency:** USD ($) *(standard convention applied as the source dataset does not specify currency)*
- **High Value:** Account Balance ≥ $100,000
- **Age Bands:** Young (<30), Adult (30–50), Senior (50+)
- **Risk Tier:** Categorized using DAX rules combining age, inactivity, geography, and product tier

---

## Project Limitations
- The dataset is a point-in-time snapshot without historical transaction logs or exact account closure dates.
- Findings represent statistically validated patterns and associations rather than proof of direct causation or individual-level churn predictions.



## Conclusion
This project combines statistical rigor in Python with executive storytelling in Power BI to pinpoint where bank churn and deposit losses are concentrated. By filtering out data leakage, quantifying financial risk, and prioritizing high-impact segments, the analysis gives retention teams a clear roadmap to protect deposits.

**Project Type:** Data Analytics  
**Technologies:** Python, Pandas, NumPy, Matplotlib, Seaborn, Power BI, DAX, Power Query  
**Author:** Riya Yadav ([GitHub](https://github.com/riyayadav16))
