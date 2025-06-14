# 🛒 SQL Sales Data Analysis Project

A comprehensive retail sales analysis project demonstrating advanced SQL Server skills through real-world business problem solving.

[![SQL Server](https://img.shields.io/badge/SQL%20Server-T--SQL-blue.svg)](https://www.microsoft.com/en-us/sql-server/)
[![Data Analysis](https://img.shields.io/badge/Data%20Analysis-Advanced-green.svg)](https://github.com/SharanPai21)

## 🎯 Project Overview

This project showcases end-to-end data analysis capabilities using SQL Server, from database setup and data cleaning to solving complex business questions. The analysis covers customer behavior, sales performance, and operational insights from retail transaction data.

## 📊 Dataset Details
- **Records**: 1000+ retail transactions
- **Time Period**: 2022-2023
- **Categories**: Beauty, Clothing, Electronics
- **Key Metrics**: Customer demographics, sales amounts, product categories, timestamps

## 🔧 Technical Implementation

### Database Setup & Data Preparation
```sql
-- Database creation and initial setup
CREATE DATABASE PROJECTSALES
USE PROJECTSALES

-- Data validation and cleaning
-- Removed NULL values across all critical fields
-- Data type optimization for performance
```

### Data Quality Assurance
- **NULL Value Handling**: Comprehensive cleanup across all columns
- **Data Type Optimization**: Converted TOTAL_SALE to FLOAT for calculations
- **Data Validation**: Verified data integrity with count checks
- **Duplicate Prevention**: Ensured unique transaction IDs

## 🔍 Business Problems Solved

### 1. **Date-Based Sales Analysis**
```sql
-- Retrieve all sales for specific date
SELECT * FROM SALES 
WHERE SALE_DATE = '2022-11-05'
```

### 2. **Category & Quantity Filtering**
```sql
-- Complex filtering with multiple conditions
SELECT * FROM SALES 
WHERE CATEGORY = 'CLOTHING' 
    AND QUANTIY >= 4  
    AND SALE_DATE >= '2022-11-01'
    AND SALE_DATE < '2022-12-01';
```

### 3. **Revenue Analysis by Category**
```sql
-- Total sales calculation by category
SELECT CATEGORY, SUM(TOTAL_SALE) FROM SALES
GROUP BY CATEGORY
```

### 4. **Customer Demographics Analysis**
```sql
-- Average age analysis for specific categories
SELECT AVG(AGE) FROM SALES 
WHERE CATEGORY = 'BEAUTY'
```

### 5. **High-Value Transaction Identification**
```sql
-- Identify premium transactions
SELECT * FROM SALES
WHERE TOTAL_SALE > 1000
```

### 6. **Gender-Based Purchase Analysis**
```sql
-- Transaction patterns by gender
SELECT GENDER, COUNT(DISTINCT TRANSACTIONS_ID) FROM SALES
GROUP BY GENDER
```

### 7. **Seasonal Trend Analysis**
```sql
-- Monthly performance with year-over-year comparison
SELECT YEAR(SALE_DATE), MONTH(SALE_DATE), AVG(TOTAL_SALE) AS AVGG 
FROM SALES
GROUP BY YEAR(SALE_DATE), MONTH(SALE_DATE)
ORDER BY AVGG DESC
```

### 8. **Customer Value Ranking**
```sql
-- Top customer identification
SELECT TOP 5 CUSTOMER_ID, SUM(TOTAL_SALE) AS SUMM 
FROM SALES 
GROUP BY CUSTOMER_ID
ORDER BY SUMM DESC
```

### 9. **Category Penetration Analysis**
```sql
-- Unique customer count per category
SELECT CATEGORY, COUNT(DISTINCT CUSTOMER_ID) AS CNT_UNIQUE_CS
FROM SALES
GROUP BY CATEGORY
```

### 10. **Cross-Category Customer Analysis**
```sql
-- Advanced: Find customers who purchased from ALL categories
SELECT COUNT(*) FROM (
    SELECT CUSTOMER_ID FROM
    (SELECT CUSTOMER_ID, COUNT(DISTINCT CATEGORY) CT FROM SALES
     GROUP BY CUSTOMER_ID) AS SUB
    WHERE CT = (SELECT COUNT(DISTINCT CATEGORY) FROM SALES)
) AS FINAL
```

### 11. **Operational Shift Analysis**
```sql
-- Time-based operational insights using CTEs
WITH HOURLY_SALE AS (
    SELECT *,
    CASE 
        WHEN DATEPART(HOUR, SALE_TIME) <= 12 THEN 'MORNING'
        WHEN DATEPART(HOUR, SALE_TIME) > 12 AND DATEPART(HOUR, SALE_TIME) <= 17 THEN 'AFTERNOON'
        ELSE 'EVENING'
    END AS SHIFT
    FROM SALES
)
SELECT SHIFT, COUNT(*) FROM HOURLY_SALE 
GROUP BY SHIFT
```

## 💻 SQL Skills Demonstrated

### **Core SQL Proficiencies**
- **Data Definition Language (DDL)**: Database and table creation, ALTER statements
- **Data Manipulation Language (DML)**: Complex SELECT, DELETE operations
- **Data Quality**: NULL handling, data type conversions, validation queries

### **Advanced Query Techniques**
- **Aggregation Functions**: SUM, COUNT, AVG with GROUP BY
- **Date Functions**: YEAR(), MONTH(), DATEPART() for temporal analysis
- **Conditional Logic**: CASE statements for dynamic categorization
- **Subqueries**: Nested queries for complex business logic
- **Common Table Expressions (CTEs)**: For readable complex queries
- **Window Functions**: DISTINCT, TOP for data ranking and filtering

### **Business Intelligence Skills**
- **Customer Segmentation**: Identifying high-value customers and behavior patterns
- **Trend Analysis**: Monthly and seasonal performance tracking
- **Operational Analytics**: Shift-based analysis for resource optimization
- **Cross-Selling Analysis**: Multi-category purchase behavior

## 📈 Key Business Insights

- **Customer Behavior**: Identified top 5 customers contributing to highest revenue
- **Category Performance**: Analyzed sales distribution across Beauty, Clothing, Electronics
- **Operational Efficiency**: Determined peak business hours (Morning/Afternoon/Evening)
- **Cross-Selling Opportunities**: Found customers purchasing across all categories
- **Seasonal Trends**: Identified best-performing months for strategic planning

## 🛠 Technical Stack
- **Database**: Microsoft SQL Server
- **Query Language**: T-SQL
- **IDE**: SQL Server Management Studio (SSMS)
- **Data Processing**: 1000+ transaction records
- **Analysis Type**: Retail sales and customer behavior analytics

## 🚀 Project Structure
```
SQL-Sales-Data-Analysis/
├── data/
│   └── sales.csv              # Raw sales dataset
├── sales_analysis.sql         # queries
└── README.md                  # Project documentation
```

## 🔍 How to Use
1. **Setup**: Create database using provided SQL scripts
2. **Import**: Load sales.csv data into SALES table
3. **Clean**: Run data cleaning and validation queries
4. **Analyze**: Execute business analysis queries to generate insights

---

**Skills Showcased**: Advanced SQL querying, data cleaning, business intelligence, customer analytics, performance optimization, and real-world problem solving through data analysis.
