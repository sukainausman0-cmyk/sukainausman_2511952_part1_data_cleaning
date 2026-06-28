# sukainausman_2511952_part1_data_cleaning
# Part 1 – Data Cleaning & Data Quality Assessment

## Overview

This project focuses on cleaning, validating, and preparing a raw retail orders dataset for reliable business analysis.

The objective was to identify data quality issues, apply appropriate cleaning techniques based on defined business rules, create calculated business metrics, and produce evaluator-friendly reports summarizing the entire cleaning process.

---

## Project Structure

```
part1_data_cleaning/
├── data/
│   ├── raw_orders.xlsx
│   └── cleaned_orders.xlsx
├── outputs/
│   ├── data_quality_report.xlsx
│   ├── pivot_summary.xlsx
│   └── cleaning_log.md
├── screenshots/
│   ├── raw_data_preview.png
│   ├── cleaned_data_preview.png
│   ├── pivot_summary_1.png
│   └── pivot_summary_2.png
└── README.md
```

---

## Data Cleaning Performed

The following data quality issues were identified and handled:

### Missing Values

- Missing Region values filled as **"Unknown"**
- Missing Ship Mode values filled as **"Unknown"**
- Missing Discount values treated as **0**

---

### Duplicate Handling

- Exact duplicate rows identified and removed.
- Duplicate Order IDs containing conflicting Sales or Order Status values were retained and flagged for manual review.

---

### Business Rule Validation

The following validation rules were applied:

- Negative discount values flagged as invalid
- Discount values validated against the allowed business range
- Ship Date occurring before Order Date identified and flagged
- Cancelled, Failed Payment, and Refunded orders categorized according to business rules

---

### Date Standardization

Dates were cleaned and standardized to ensure consistent formatting.

Additional date-based fields were created:

- Order Month
- Order Year
- Shipping Delay (Days)

---

### Calculated Columns Created

The following business metrics were generated:

- cleaned_discount
- calculated_sales
- calculated_profit
- profit_margin
- shipping_delay_days
- order_month
- order_year
- data_quality_flag

Additional helper columns were also created where required to support data validation and reporting.

---

## Data Quality Reports

A comprehensive data quality report was prepared containing:

- Missing Value Summary
- Duplicate Summary
- Invalid Discount Summary
- Date Issue Summary
- Order Status Issue Summary
- Sales / Profit Calculation Mismatch Summary
- Final Clean vs Flagged Record Count

---

## Pivot Summary Report

Business summary reports were created using Pivot Tables, including:

- Sales and Profit by Region
- Sales and Profit by Category and Sub-category
- Order Count by Ship Mode
- Profit Margin by Customer Segment
- Refunded / Cancelled / Failed Orders by Region
- Monthly Sales Trend

Sorting and filtering were applied where appropriate to improve report readability.

---

## Assumptions

The following assumptions were made during the cleaning process:

- Missing Region values represent unknown locations.
- Missing Ship Mode values were replaced with "Unknown."
- Missing Discount values indicate no discount applied.
- Invalid records were flagged instead of deleted unless they were confirmed exact duplicates.
- Conflicting duplicate Order IDs were retained for manual business review.

---

## Deliverables

This submission includes:

- Cleaned dataset
- Data quality assessment report
- Business pivot summaries
- Cleaning log
- Supporting screenshots
- Project documentation

---

## Tools Used

- Microsoft Excel
- Power Query
- Pivot Tables
- Git & GitHub
- Visual Studio Code

---

## Author

**Sukaina Usman**

