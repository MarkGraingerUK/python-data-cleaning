# Python Data Cleaning Pipeline & Automated Workflow

## Project Overview

Data quality is the foundation of any reliable analysis, business intelligence dashboard, or machine learning model. This repository showcases a robust, automated data cleaning pipeline built using **Python** and **Pandas**. 

The script ingests a raw, unvalidated retail sales dataset containing anomalies, inconsistent text casing, whitespace issues, missing values, and corrupted date formats, and systematically transforms it into a pristine, analysis-ready structure.

---

## Key Objectives

* **Standardize Inconsistent Data:** Clean messy string entries, fix mixed-case formatting, and eliminate trailing or leading whitespace.
* **Handle Missing & Corrupt Data:** Address non-numeric financial figures, map missing entries to reliable defaults, and manage invalid timestamp strings.
* **Automate & Validate:** Execute a repeatable end-to-end pipeline that verifies dataset shapes before and after transformation, outputting clean CSV files ready for downstream tools like Power BI or SQL Server.

---

## Detailed Processing Steps

### 1. Ingestion & Shape Inspection
* Loads raw transaction records from `shop_sales_raw.csv`.
* Prints the initial dimensions of the dataset to establish a baseline row and column count.

### 2. String Standardization
* Applies string manipulation functions (`.str.strip()`, `.str.title()`, `.str.capitalize()`) to customer names and transaction statuses to ensure uniformity across reporting views.

### 3. Data Type Coercion & Missing Value Treatment
* **Financials (`total_price`):** Converts mixed or text-based currency fields into numeric floating-point values using error coercion (`errors='coerce'`), safely filling resulting NaN values with `0.0`.
* **Timestamps (`order_date`):** Replaces placeholder strings (such as `'NA'`) with proper null values (`np.nan`), drops rows where critical date entries are missing, and casts the remaining records into standard datetime objects.

### 4. Output & Console Verification
* Exports the finalized, validated dataset to `shop_sales_cleaned.csv`.
* Prints the post-transformation dataset shape and renders a formatted preview directly to the console or notebook output without index clutter.

---

## Tech Stack & Tools

* **Language:** Python
* **Library:** Pandas (Data manipulation and structuring)
* **Library:** NumPy (Numerical operations and handling NaN values)
* **Environment:** Google Colab / Jupyter Notebook

---

## Repository Structure

python-data-cleaning/
* **python_data_cleaning.ipynb**   - Interactive Jupyter Notebook containing the full code and output preview
* **shop_sales_raw.csv**           - Original raw dataset with intentional anomalies and dirty data
* **shop_sales_cleaned.csv**       - Fully processed, validated, and standardized dataset

