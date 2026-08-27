# 🛒 E-Commerce Sales Analysis & Power BI Dashboard

## 📌 Project Overview

This project analyzes e-commerce sales data to understand overall sales performance, revenue trends, customer purchasing behavior, product/category performance, and geographic sales distribution.

The project uses **Python for data preparation and exploratory sales analysis** and **Power BI for interactive dashboarding and business reporting**.

The objective is to transform raw e-commerce transaction data into meaningful business insights that can help an e-commerce business make better decisions around sales performance, products, customers, and operations.

---

## 🎯 Business Problem

An e-commerce business generates a large volume of transactional data, but raw data alone does not provide clear answers to important business questions.

This project aims to answer questions such as:

- How much revenue is the business generating?
- How are sales changing month over month?
- How many orders are being placed?
- What is the Average Order Value (AOV)?
- Which product categories generate the most revenue?
- Which products generate the highest revenue?
- Which states contribute the most revenue?
- Where are orders concentrated geographically?
- How does freight cost vary across product categories?
- What areas of sales performance require attention?

---

# 🛠️ Tools & Technologies

- **Python**
  - Pandas
  - NumPy
  - Matplotlib
  - Seaborn
- **Power BI**
  - Power Query
  - DAX
  - Data Modeling
  - Interactive Visualizations
- **Jupyter Notebook**
- **Git & GitHub**

---

# 📂 Dataset

The project uses the **Brazilian E-Commerce Public Dataset by Olist**.

The dataset contains information related to:

- Orders
- Customers
- Products
- Sellers
- Payments
- Order items
- Reviews
- Geolocation
- Product categories

The raw dataset contains multiple related tables that were combined during the data preparation process to create an analysis-ready sales dataset.

---

# 🗂️ Project Structure

```text
ecommerce-sales-analysis/
│
├── data/
│   ├── raw/
│   │   └── Olist dataset files
│   │
│   └── processed/
│       └── sales_base.csv
│
├── notebooks/
│   └── ecommerce_sales_analysis.ipynb
│
├── powerbi/
│   └── ecommerce_sales_dashboard.pbix
│
├── images/
│   ├── sales_overview.png
│   └── sales_performance.png
│
└── README.md
