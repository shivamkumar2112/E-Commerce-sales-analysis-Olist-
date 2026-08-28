# 🛒 E-Commerce Sales Analysis & Power BI Dashboard

## 📌 Project Overview

This project is an end-to-end E-Commerce Sales Analysis project built using Python and Power BI.

The objective is to analyze e-commerce transaction data, identify important sales trends and performance patterns, calculate key business metrics, and present the findings through an interactive Power BI dashboard.

The project starts with raw e-commerce data, performs data understanding and data-quality checks in Python, prepares an analysis-ready sales dataset, and then uses Power BI for data modeling, KPI creation, and dashboard development.

---

## 🎯 Business Objective

The main objective of this project is to understand the sales performance of an e-commerce business.

The analysis focuses on the following business questions:

- How much revenue is being generated?
- How many orders are being placed?
- How many items are being sold?
- What is the Average Order Value (AOV)?
- How does revenue change over time?
- How does order volume change over time?
- Which product categories generate the highest revenue?
- Which products generate the highest revenue?
- Which states generate the highest revenue?
- Which states have the highest number of orders?
- Which product categories have higher average freight costs?

---

## 📊 Dataset

The project uses the Brazilian E-Commerce Public Dataset by Olist.

The dataset contains multiple related tables covering different aspects of the e-commerce business, including:

- Orders
- Order Items
- Customers
- Products
- Sellers
- Payments
- Reviews
- Geolocation
- Product Category Translation

The available tables were first inspected individually to understand their structure and data quality. Relevant tables were then combined and transformed to create the sales dataset used for analysis.

---

## 🛠️ Tools & Technologies

### Python

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

### Power BI

- Power Query
- DAX
- Data Modeling
- KPI Cards
- Charts
- Slicers

### Version Control

- Git
- GitHub

---

## 🔄 Project Workflow

Raw E-Commerce Data → Data Understanding → Data Quality Checks → Missing Value Analysis → Duplicate Checks → Data Cleaning → Data Transformation → Creation of Sales Dataset → Sales Analysis using Python → Power BI Data Modeling → DAX Measures → Interactive Dashboard → Business Insights

---

# 🐍 Python Data Analysis

## 1. Data Understanding

Before performing the sales analysis, the available Olist tables were examined individually.

The following checks were performed:

- Dataset shape
- Column names
- Data types
- Dataset information using `info()`
- Statistical summary using `describe()`
- Missing-value analysis
- Duplicate checks
- Unique-value checks

This helped identify potential data-quality issues before moving into the sales analysis.

---

## 2. Data Cleaning and Preparation

The required datasets were cleaned and prepared before performing the sales analysis.

The preparation included:

- Handling missing values
- Checking duplicate records
- Converting date and time columns
- Validating numeric columns
- Checking data consistency
- Selecting required columns
- Combining relevant tables
- Creating an analysis-ready sales dataset

The resulting dataset used for the analysis was `sales_base`.

---

## 3. Date Preparation

The original transaction timestamp used in the dataset is `order_purchase_timestamp`.

A separate `Order Date` field was created from the transaction timestamp.

The `Order Date` field was used for date-based sales analysis and Power BI data modeling.

A dedicated Date Table was also created in Power BI to support time-based analysis.

---

# 📈 Sales Analysis

## 1. Total Revenue

Total revenue was calculated from the product price associated with order items.

The Power BI DAX measure used was:

`Total Revenue = SUM(sales_base[price])`

This metric represents the total sales revenue analyzed in the dataset.

---

## 2. Total Orders

The total number of unique orders was calculated using `order_id`.

The Power BI DAX measure used was:

`Total Orders = DISTINCTCOUNT(sales_base[order_id])`

This metric represents the number of unique orders.

---

## 3. Units Sold

The total number of order items was used to calculate the number of units/items sold.

The Power BI DAX measure used was:

`Units Sold = COUNT(sales_base[order_item_id])`

---

## 4. Average Order Value (AOV)

Average Order Value measures the average revenue generated per order.

The formula used was:

`AOV = Total Revenue / Total Orders`

The Power BI DAX measure used was:

`AOV = DIVIDE([Total Revenue], [Total Orders])`

---

## 5. Total Freight

Total freight value was calculated to understand the overall freight amount associated with the analyzed order items.

The Power BI DAX measure used was:

`Total Freight = SUM(sales_base[freight_value])`

---

## 6. Average Freight

Average freight value was calculated to compare freight costs across product categories.

The Power BI DAX measure used was:

`Average Freight = AVERAGE(sales_base[freight_value])`

---

# 📅 Time-Based Sales Analysis

## Monthly Revenue Trend

Revenue was analyzed month by month to understand how sales changed over time.

The analysis helps identify:

- High-revenue periods
- Low-revenue periods
- Changes in sales performance
- Overall revenue trends

A dedicated Date Table was created in Power BI for time-based analysis.

The Date Table contains:

- Date
- Year
- Month Number
- Month
- Year Month
- YearMonthSort

The `YearMonthSort` field was used to ensure that months appear in chronological order instead of alphabetical order.

---

## Monthly Orders Trend

Order volume was analyzed month by month.

Comparing monthly orders with monthly revenue helps understand whether changes in revenue are associated with changes in order volume.

---

# 📦 Category Sales Analysis

## Top 10 Categories by Revenue

Revenue was analyzed across product categories to identify the categories contributing the most to total sales.

A Top 10 analysis was used to focus on the highest-revenue categories.

This provides a clear view of the major category-level contributors to sales.

---

# 🏆 Product Sales Analysis

## Top 10 Products by Revenue

Product-level sales revenue was analyzed to identify products generating the highest revenue.

A Top 10 analysis was used to highlight the highest-revenue products.

This helps identify individual products that make a significant contribution to overall sales.

---

# 🌎 Geographic Sales Analysis

## Revenue by State

Revenue was analyzed across Brazilian states to understand the geographic distribution of sales.

This helps identify states contributing the most to overall revenue.

---

## Orders by State

Order volume was also analyzed across Brazilian states.

Comparing revenue and order volume provides a broader understanding of geographic sales performance.

---

# 🚚 Freight Analysis

## Average Freight by Category

Average freight value was analyzed across product categories.

The purpose of this analysis is to identify categories where average freight costs are relatively higher.

A Top 10 view was used to make the comparison easier to interpret.

---

# 📊 Power BI Dashboard

The analysis was transformed into an interactive Power BI dashboard consisting of two pages.

---

## Page 1 — Sales Overview

The Sales Overview page provides a high-level view of overall sales performance.

### KPI Cards

- Total Revenue
- Total Orders
- Units Sold
- Average Order Value

### Visualizations

- Monthly Revenue Trend
- Monthly Orders Trend
- Top 10 Categories by Revenue
- Top 10 Products by Revenue

### Purpose

This page provides a quick overview of the most important sales KPIs and sales trends.

---

## Page 2 — Sales Performance

The Sales Performance page provides a more detailed view of geographic and freight-related sales performance.

### Visualizations

- Revenue by State
- Orders by State
- Average Freight by Category

### Slicers

- Year
- Product Category
- Customer State

The slicers allow users to interactively filter the dashboard and explore sales performance across different years, categories, and states.

---

# 🗓️ Power BI Date Table

A dedicated Date Table was created in Power BI using the minimum and maximum `Order Date` values from the sales dataset.

The Date Table was used for time-based analysis and chronological sorting of monthly sales data.

The relationship created in the Power BI model is:

`DateTable[Date] → sales_base[Order Date]`

with a one-to-many relationship from the Date Table to the sales table.

---

# 🧮 Key DAX Measures

### Total Revenue

`Total Revenue = SUM(sales_base[price])`

### Total Orders

`Total Orders = DISTINCTCOUNT(sales_base[order_id])`

### Units Sold

`Units Sold = COUNT(sales_base[order_item_id])`

### Average Order Value

`AOV = DIVIDE([Total Revenue], [Total Orders])`

### Total Freight

`Total Freight = SUM(sales_base[freight_value])`

### Average Freight

`Average Freight = AVERAGE(sales_base[freight_value])`

---

# 📸 Power BI Dashboard Preview

## Sales Overview

<img width="1122" height="730" alt="Screenshot 2026-08-28 231718" src="https://github.com/user-attachments/assets/c3e1c31a-9d34-4060-9e4f-78682d3c55e3" />


## Sales Performance

<img width="1247" height="728" alt="Screenshot 2026-08-28 231746" src="https://github.com/user-attachments/assets/8568f125-31f6-4d4d-9a4c-16ec300a42b1" />


---

# 🔎 Business Questions Addressed

| Business Question | Metric / Analysis |
|---|---|
| How much revenue is generated? | Total Revenue |
| How many orders are placed? | Total Orders |
| How many items are sold? | Units Sold |
| What is the average order value? | AOV |
| How does revenue change over time? | Monthly Revenue Trend |
| How does order volume change over time? | Monthly Orders Trend |
| Which categories generate the most revenue? | Top 10 Categories by Revenue |
| Which products generate the most revenue? | Top 10 Products by Revenue |
| Which states generate the most revenue? | Revenue by State |
| Which states have the highest order volume? | Orders by State |
| Which categories have higher average freight costs? | Average Freight by Category |

---

# 💡 Business Value

This analysis converts raw e-commerce transaction data into a structured view of sales performance.

The dashboard provides a practical way to:

- Monitor key sales KPIs
- Track revenue trends
- Track order volume
- Understand Average Order Value
- Identify high-revenue categories
- Identify high-revenue products
- Compare sales across states
- Compare order volumes across states
- Identify categories with higher average freight costs
- Support data-driven sales decisions

---

# 📁 Repository Structure

ecommerce-sales-analysis/

├── data/

│   └── sales_base.csv

├── notebooks/

│   └── sales_analysis.ipynb

├── images/

│   ├── sales_overview.png

│   └── sales_performance.png

└── README.md

The Power BI `.pbix` file is not included in this repository. Dashboard screenshots are included to showcase the final dashboard.

---

# 📌 Project Highlights

**Project Type:** E-Commerce Sales Analysis

**Domain:** E-Commerce

**Dataset:** Brazilian E-Commerce Public Dataset by Olist

**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, Power BI, DAX

**Core KPIs:**

- Total Revenue
- Total Orders
- Units Sold
- Average Order Value
- Total Freight
- Average Freight

**Key Analyses:**

- Monthly Revenue Trend
- Monthly Orders Trend
- Top 10 Categories by Revenue
- Top 10 Products by Revenue
- Revenue by State
- Orders by State
- Average Freight by Category

**Dashboard Pages:**

1. Sales Overview
2. Sales Performance

---

# 👨‍💻 Project Outcome

This project demonstrates an end-to-end approach to e-commerce sales analysis, starting from raw transactional data and ending with an interactive Power BI dashboard.

The project demonstrates practical experience in:

- Data understanding
- Data-quality analysis
- Missing-value analysis
- Duplicate checking
- Data cleaning
- Data transformation
- Sales performance analysis
- KPI calculation
- Time-based analysis
- Geographic sales analysis
- Freight analysis
- Power BI data modeling
- DAX
- Interactive dashboard development
- Business-focused data visualization

The final dashboard provides a clear and interactive view of e-commerce sales performance and allows users to explore the data using different filters and business dimensions.
