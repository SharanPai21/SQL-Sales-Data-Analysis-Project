# 🛒 SQL-Sales-Data-Analysis-Project

Welcome to the **Retail Sales Analysis** project! This repository showcases a complete end-to-end data exploration and business insight generation process using **Microsoft SQL Server (SSMS)**. The dataset simulates sales transactions for a retail business — your typical mix of customers, products, and purchase behavior — and this project dives deep into uncovering patterns, trends, and answers to key business questions.

---

## 📂 Project Structure

```plaintext
├── data/
│   └── sales.csv              # Raw dataset (uploaded by user)
├── sales_analysis.sql         # SQL script for data cleaning & analysis
└── README.md                  # You're here!
💡 Objectives
This project was built to practice and demonstrate:

Writing efficient SQL queries

Performing data cleaning and transformation

Extracting meaningful business insights

Applying groupings, aggregations, subqueries, and window functions

Using SQL Server's built-in functions for dates, formatting, and logic

🧰 Tools Used
Microsoft SQL Server Management Studio (SSMS)

SQL (T-SQL dialect)

Basic Git and GitHub for version control

🔍 Key Business Questions Answered
The SQL script (sales_analysis.sql) addresses real-world business queries such as:

Retrieve all sales made on a specific date.

Find transactions from a specific category with quantity conditions.

Calculate total sales by category.

Determine the average age of beauty product customers.

Identify high-value transactions (total_sale > 1000).

Analyze transactions made by gender in each category.

Discover the best-selling months based on average sales.

Identify the top 5 customers by total spending.

Count how many unique customers bought items in each category.

Find customers who purchased from every category (not just one).

Classify each transaction into Morning, Afternoon, or Evening based on time.

🔎 Sample Insights
Which category has the highest customer engagement?

Who are the most valuable customers?

What time of day sees the highest order volume?

Which month generates the most revenue?

📈 Skills Demonstrated
Data filtering, grouping, and aggregation

Subqueries and common table expressions (CTEs)

Data validation and NULL handling

Case statements for dynamic categorization

Working with temporal data (dates and times)

✅ How to Use
Clone the repository:

git clone https://github.com/SharanPai21/SQL-Sales-Data-Analysis-Project

Open sales_analysis.sql in SSMS.

Connect to your local SQL Server.

Run the script step by step to:

Create and use the database

Clean the data

Analyze and visualize trends

📌 Notes
The dataset is already available under the data/ folder.

The analysis assumes that the dataset has been imported into a table named sales.

All SQL was written and tested using SQL Server 2019 via SSMS.
