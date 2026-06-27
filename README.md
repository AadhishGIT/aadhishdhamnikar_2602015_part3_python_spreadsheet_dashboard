# Spreadsheet Data Cleaning, Pivot Analysis and Business Dashboard

## Student Details

**Assignment:** Part 3 – Spreadsheet Data Cleaning, Pivot Analysis and Dashboard

**Student Name:** Aadhish Dhamnikar

**Student ID:** 2602015

---

# Repository Structure

```
studentname_studentid_part3_spreadsheet_dashboard/
│
├── README.md
├── raw_data/
│   ├── customers_raw.xlsx
│   ├── orders_raw.xlsx
│   └── products_raw.xlsx
├── cleaned_data/
│   ├── customers_cleaned.xlsx
│   ├── orders_cleaned.xlsx
│   └── products_cleaned.xlsx
├── analysis/
│   ├── cleaning_log.xlsx
│   └── pivot_analysis.xlsx
├── dashboard/
│   └── business_dashboard.xlsx
└── outputs/
    └── screenshots/
```

---

# Dataset Overview

The project consists of three related business datasets used to analyze sales performance, customer behavior, and product performance.

### Customers Dataset
Contains customer master information including:

- Customer ID
- Customer Name
- Email
- Phone Number
- City
- Region
- Customer Segment

### Products Dataset

Contains product master information including:

- Product ID
- Product Name
- Product Category
- Cost Price
- Selling Price

### Orders Dataset

Contains transactional sales data including:

- Order ID
- Customer ID
- Product ID
- Order Date
- Quantity
- Unit Price
- Payment Method
- Order Status

---

# Relationship Between the Three Datasets

The datasets are connected using primary and foreign keys.

```
Customers
(Customer ID)
      │
      │
      ▼
Orders
(Customer ID, Product ID)
      ▲
      │
      │
Products
(Product ID)
```

- **Customer ID** links Customers and Orders.
- **Product ID** links Products and Orders.

Power Query Merge was used to combine these datasets for analysis.

---

# Raw Data Issues Identified

The following issues were identified in the raw datasets:

### Customers

- Duplicate Customer IDs
- Missing Customer Names
- Missing Email Addresses
- Invalid Email Formats
- Invalid Phone Numbers
- Inconsistent City Names
- Inconsistent Region Names
- Inconsistent Customer Segments
- Leading and Trailing Spaces
- Inconsistent Text Casing

### Products

- Duplicate Product IDs
- Missing Product Names
- Inconsistent Product Categories
- Missing/Negative Selling Prices
- Cost Price Higher Than Selling Price

### Orders

- Duplicate Order IDs
- Invalid Customer IDs
- Invalid Product IDs
- Missing/Negative Quantities
- Missing/Negative Unit Prices
- Unit Price Mismatch
- Invalid Order Status
- Invalid Payment Methods
- Invalid Date Formats

---

# Cleaning Approach

Data cleaning was performed using **Microsoft Excel Power Query**.

The following transformations were applied:

- Removed duplicate records
- Trimmed extra spaces
- Cleaned hidden characters
- Standardized text casing
- Standardized city names
- Standardized region names
- Standardized customer segments
- Standardized product categories
- Validated email addresses
- Validated phone numbers
- Validated Customer IDs
- Validated Product IDs
- Validated quantities
- Validated unit prices
- Compared selling prices with product master
- Created validation flags
- Added calculated business fields

---

# Summary of Cleaning Decisions

The following decisions were taken during data cleaning:

- Duplicate master records were removed.
- Missing customer names were replaced with **"Unknown Customer"**.
- Missing product names were replaced with **"Unknown Product"**.
- Invalid emails and phone numbers were flagged instead of deleted.
- Invalid customer and product references were identified using Merge Queries.
- Invalid quantities and prices were validated using custom columns.
- Product categories, city names, regions, and customer segments were standardized.
- Revenue, Gross Profit, Gross Profit %, Estimated Cost, Month, and validation flags were created for analysis.

---

# Pivot Analysis Questions Answered

The following Pivot Tables were created:

1. Total Revenue by Product Category
2. Gross Profit by Product Category
3. Revenue by Region
4. Revenue by Customer Segment
5. Average Order Value by City
6. Number of Orders by Payment Method
7. Completed vs Cancelled Orders
8. Monthly Revenue Trend
9. Top 10 Customers by Revenue
10. Top 10 Products by Quantity Sold
11. Revenue Loss from Cancelled Orders
12. Invalid Orders by Issue Type

---

# Dashboard Explanation

The dashboard was developed using Pivot Tables, Pivot Charts, KPI Cards, and Slicers.

### KPI Cards

- Total Revenue
- Gross Profit
- Total Orders
- Cancelled Orders

### Visualizations

- Revenue by Product Category
- Revenue by Region
- Monthly Revenue Trend
- Order Status Distribution
- Top 10 Products by Quantity Sold

### Interactive Filters

The dashboard includes slicers for:

- Region
- Customer Segment
- Product Category

These slicers allow users to interactively filter all charts simultaneously.

---

# Business Insights

The dashboard generated the following key insights:

1. Office Supplies contributes the highest revenue among all product categories.
2. West region generates the highest sales revenue.
3. Most customer orders are successfully completed.
4. Office Supplies is the best-selling product category based on quantity sold.
5. Revenue peaks during May, indicating the strongest monthly sales performance.

---

# Screenshots

The following screenshots have been included inside:

```
outputs/screenshots/
```

The screenshots include:

- Raw Data Sample
- Cleaned Customers Data
- Cleaned Products Data
- Cleaned Orders Data
- Cleaning Log
- Pivot Table Analysis
- Business Dashboard

---

# Assumptions Made

The following assumptions were made during data cleaning and analysis:

- Customer IDs and Product IDs are unique identifiers.
- Missing customer names were replaced with **"Unknown Customer"**.
- Missing product names were replaced with **"Unknown Product"**.
- Email addresses were validated using standard email format checks.
- Quantities less than or equal to zero were considered invalid.
- Unit prices less than or equal to zero were considered invalid.
- Product master data was considered the source of truth for selling prices.
- Product categories, customer segments, city names, and region names were standardized before analysis.
- All calculated fields (Revenue, Cost, Gross Profit, Gross Profit %, and Validation Flags) were generated after cleaning.

---

# Tools Used

- Microsoft Excel
- Power Query
- Pivot Tables
- Pivot Charts
- Slicers
- Excel Dashboard

---

# Conclusion

This project demonstrates the complete business analytics workflow, including data cleaning, validation, transformation, exploratory analysis, Pivot Table reporting, and dashboard creation using Microsoft Excel and Power Query. The final dashboard provides an interactive summary of business performance, customer behavior, product performance, and operational quality.
