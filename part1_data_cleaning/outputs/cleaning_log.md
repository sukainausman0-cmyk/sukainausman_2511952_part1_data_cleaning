# Data Cleaning Log

## Dataset Overview

The dataset was cleaned to improve data quality, consistency, and reliability before performing analysis and creating summary reports. Duplicate records, missing values, invalid values, and inconsistent records were identified and handled according to predefined business rules.

---

# 1. Issues Found

The following data quality issues were identified:

* Missing Region values
* Missing Ship Mode values
* Missing Discount values
* Negative Discount values
* Discount values above the allowed range
* Cancelled Orders
* Failed Payments
* Refunded Orders
* Ship Date earlier than Order Date
* Exact Duplicate Records
* Duplicate Order IDs with conflicting Sales or Order Status values

---

# 2. Cleaning Actions Performed

The following cleaning steps were applied:

* Filled missing Region values with **"Unknown"**.
* Filled missing Ship Mode values with **"Unknown"**.
* Replaced missing Discount values with **0**.
* Standardized discount values using a cleaned discount column.
* Flagged negative discount records as invalid.
* Checked for discounts above the allowed range (>100%).
* Created calculated Sales and Profit columns.
* Calculated Profit Margin.
* Calculated Shipping Delay Days.
* Extracted Order Month and Order Year.
* Created Data Quality Flag to identify clean, warning, and invalid records.
* Removed exact duplicate records.
* Retained conflicting duplicate Order IDs and flagged them for manual review.
* Excluded Cancelled and Failed Payment orders from completed sales summaries.
* Created a separate summary for Refunded Orders.
* Flagged records where Ship Date occurred before Order Date.

---

# 3. Business Rules Applied

The following business rules were used during cleaning:

* Missing Region → Filled as **Unknown**
* Missing Ship Mode → Filled as **Unknown**
* Missing Discount → Treated as **0**
* Negative Discount → Flagged as Invalid
* Discount must not exceed 100%
* Ship Date should not be earlier than Order Date
* Exact duplicate rows were removed
* Duplicate Order IDs with conflicting information were retained for manual review
* Cancelled and Failed Payment orders were excluded from completed sales summaries
* Refunded Orders were summarized separately

---

# 4. Assumptions Made

* Missing discounts indicate no discount was applied.
* Unknown Region and Ship Mode are preferable to deleting records.
* Negative discounts are treated as invalid rather than corrected.
* Conflicting duplicate Order IDs may represent genuine business cases and therefore require manual review.
* Refunded orders are retained for reporting but excluded from completed sales analysis.

---

# 5. Records Removed

* Exact duplicate rows removed: **20**

---

# 6. Records Flagged

The following records were flagged instead of removed:

* Negative Discount records
* Ship Date before Order Date records
* Duplicate Order IDs with conflicting Sales or Order Status values
* Missing Region records
* Missing Ship Mode records
* Missing Discount records

---

# 7. Limitations

* Missing values were filled using business assumptions rather than external data.
* Invalid shipping dates were flagged but not corrected due to lack of reliable information.
* Duplicate Order IDs with conflicting information require manual business validation.
* The cleaning process assumes the available dataset is the only source of truth.
* Business rules may vary depending on organizational requirements.

---

# Summary

The cleaned dataset is standardized, documented, and suitable for downstream analysis, reporting, and dashboard creation while preserving records requiring manual review.
