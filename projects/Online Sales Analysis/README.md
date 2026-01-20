# E-Commerce Transaction Analysis with SQL

## 📊 Project Overview
This project demonstrates SQL-based data analysis using a simulated real-world e-commerce dataset from Kaggle. The objective is to clean, explore, and analyze transactional data to answer business-driven questions.

## 🧰 Tools Used
- SQL (MySQL)
- Kaggle Dataset
- Microsoft Excel

## 📁 Dataset
Source: [Kaggle - Online Shop 2024 Dataset](https://www.kaggle.com/datasets/marthadimgba/online-shop-2024/data)
The dataset contains eight interconnected tables which are:
- customers
- orders
- order_items
- products
- suppliers
- payments
- reviews
- shipments

## 🧹 Data Cleaning

Initial data cleaning was performed prior to database ingestion using Excel to ensure data consistency and smooth import into MySQL.

Steps included:
- Extracted state codes from the address field and created a new `state_code` column
- Standardized phone numbers into `XXX-XXX-XXXX` format

For detailed formulas and step-by-step Excel instructions, see
[`data-cleaning/excel_formulas.md`](data-cleaning/excel_formulas.md)

Post-ingestion validation and analysis were then performed using SQL.

## 🗂 Database Schema

Tables were imported into MySQL using MySQL Workbench’s Table Data Import Wizard. Primary keys (PKs) and foreign key (FK) relationships were then defined using the Workbench GUI to enforce referential integrity and accurately model real-world
business relationships.

Key relationships include:
- Each customer can place multiple orders
- Each order can contain multiple order items
- Products are supplied by suppliers and can appear in multiple orders
- Orders are associated with payments and shipments
- Customers and products can receive multiple reviews

The Entity-Relationship (ER) diagram below illustrates the database structure and relationships between all tables.

![ER Diagram](https://github.com/user-attachments/assets/a067f41e-2f04-4cba-b32f-5797d8f5e144)

## ❓ Business Questions
- Which products generate the highest revenue?
- Who are the top customers by lifetime value?
- Which suppliers contribute most to sales?
- What are the monthly sales trends?

## 📈 Key Insights
- Top 10 products contribute a significant portion of total revenue
- Repeat customers show higher average order values
- Certain suppliers dominate sales performance

Detailed findings are available in [`results/findings.md`](results/findings.md)

## 📂 Project Structure
```text
Online Sales Analysis/
├── data-cleaning/
│   └── excel_formulas.md   # Detailed Excel formulas and steps
│
├── sql/
│   ├── 01_data_validation.sql # SQL checks to validate cleaned data
│   └── 02_analysis.sql        # Queries answering business questions
│
├── results/
│   └── findings.md            # Summary of results and insights
│
└── README.md                  # Project documentation
