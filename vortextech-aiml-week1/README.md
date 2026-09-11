# Café Sales Exploratory Data Analysis (EDA) & Data Cleaning

## 📌 Project Overview
This project focuses on performing Data Cleaning and Exploratory Data Analysis (EDA) on a dataset containing café sales transactions (`dirty_cafe_sales.csv`). The objective is to identify data quality issues, handle missing values, resolve inconsistent data types, detect outliers, and generate key business insights using Python data analysis libraries.

---

## 🛠️ Tech Stack & Libraries
* **Language:** Python 3.x
* **Environment:** Visual Studio Code / Jupyter Notebook
* **Libraries Used:**
  * `pandas` - Data manipulation and cleaning
  * `numpy` - Numerical computations
  * `matplotlib` - Static visualizations
  * `seaborn` - Advanced statistical visual graphs

---

## 🚀 Data Processing Pipeline

### 1. Data Ingestion & Pre-inspection
* Loaded raw dataset consisting of 10,000 transaction records.
* Inspected initial data structure using `df.info()` and `df.describe()`.
* Identified that all 8 columns were initially loaded as generic `object` (string) data types.

### 2. Data Cleaning & Type Casting
* **Numeric Conversion:** Converted `Quantity`, `Price Per Unit`, and `Total Spent` columns from string format to numerical (`float64`/`int64`).
* **Missing Value Imputation:**
  * Used **Median** imputation for numerical variables (`Quantity`, `Price Per Unit`, `Total Spent`) to avoid bias from extreme values.
  * Used **Mode** imputation for categorical variables (`Item`, `Payment Method`, `Location`, `Transaction Date`).
* **Duplicate Removal:** Checked full row duplicates via `df.duplicated().sum()`. Confirmed zero duplicate rows.

### 3. Exploratory Data Analysis & Visualizations
* **Histograms:** Plotted continuous metric distributions to analyze purchase volumes and spending spreads.
* **Bar Charts / Countplots:** Visualized category frequencies across `Item`, `Location`, and `Payment Method` columns.
* **Outlier Detection:** Computed Interquartile Range (IQR) bounds and plotted boxplots. Identified 259 high-value transactions in `Total Spent` which were preserved as valid high-volume purchases.

---

## 📈 Key Insights & Findings

1. **Transaction Patterns:** Most customers purchase between 1 to 5 units per order, with a median quantity of 3 units.
2. **Revenue Distribution:** Average spent per transaction is around $8.88.
3. **Valid Extreme Values:** The 259 detected outliers in `Total Spent` represent legitimate bulk purchases rather than data logging errors.
4. **Data Integrity:** Post-cleaning dataset reached 100% complete entries across all 10,000 rows without structural data loss.

---

## 📁 Repository Structure

```text
├── dirty_cafe_sales.csv      # Raw dataset (Input)
├── cleaned_cafe_sales.csv    # Processed & cleaned dataset (Output)
├── EDA.ipynb                 # Main Jupyter notebook containing data pipeline & graphs
└── README.md                 # Project documentation