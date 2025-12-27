# transaction
Power BI project: transactions— data cleaning, currency normalization, dashboard.
# Power BI – Power Query Data Transformation Project

## Overview

This project focuses on cleaning, transforming, and restructuring transactional banking data using **Power Query in Power BI**.
The objective was to convert inconsistent and poorly structured raw data into clean, analysis-ready tables and produce meaningful aggregated insights.

This project is based on a hands-on Power Query transformation assignment and demonstrates practical data-wrangling skills rather than dashboard design.

---

## Datasets Used

* `fact_transactions_2022`
* `fact_transactions_2023`
* `dim_merchants`
* `dim_date`
* `pivoted_dim_category`

---

## Key Data Transformation Tasks

### 1. Merchant Data Cleaning (`dim_merchants`)

* Split merchant names to extract **Industry Segment**
* Trimmed unnecessary spaces
* Removed special characters like `(` and `)`
* Eliminated duplicate merchants with different IDs

---

### 2. Date Dimension Enhancement (`dim_date`)

* Extracted:

  * Year
  * Month Name
  * Day Name
* Created a structured date dimension suitable for time-based analysis

---

### 3. Category Table Restructuring

* Transposed and unpivoted the category table
* Converted wide, non-relational format into a clean lookup table
* Renamed final table to `dim_category`

---

### 4. Filtering Insignificant Transactions

* Removed all transactions with **Debit Amount < 100**
* Applied filtering consistently across 2022 and 2023 datasets

---

### 5. Appending Yearly Data

* Appended `fact_transactions_2023` to `fact_transactions_2022`
* Created a consolidated table named `fact_transactions`

---

### 6. Table Merging

* Merged `fact_transactions` with:

  * `dim_merchants`
  * `dim_category`
* Enriched fact data with merchant and category names

---

### 7. Conditional Column Creation

* Added **Transaction Category** column:

  * `Low` → Debit Amount < 1000
  * `High` → Debit Amount ≥ 1000

---

### 8. Aggregation & Analysis

* Grouped data by **Merchant**
* Calculated **Total Transaction Amount per Merchant**
* Sorted merchants in descending order based on total transaction value

---

## Final Output

A clean, aggregated table showing total transaction amount per merchant:

* One row per merchant
* Pre-aggregated using Power Query
* Ready for reporting or further modeling

---

## Tools & Concepts Used

* Power BI
* Power Query (M Language)
* Data Cleaning & Transformation
* Filtering & Appending
* Table Merging
* Grouping & Aggregation

---

## Notes

* Aggregations were intentionally performed in **Power Query** to demonstrate data transformation skills.
* No DAX measures were used for this analysis.
* The focus of this project is **data preparation**, not interactive dashboards.

---

## Learning Outcome

This project strengthened understanding of:

* Real-world data inconsistencies
* When to use Power Query vs DAX
* Building clean fact and dimension tables
* Preparing data for scalable BI models
## Dashboard Preview

![Total Transaction Amount by Merchant](report/fact_transactions.png)
