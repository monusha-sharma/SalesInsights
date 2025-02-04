# Sales Insights — Brick & Mortar Business (Power BI & SQL)

## Project Overview
This project involves designing a **Power BI dashboard** to analyze sales trends for **AtliQ Hardware**, a brick-and-mortar business. The final dashboard effectively visualizes sales trends, enabling data-driven decision-making. 

This dashboard has the potential to **increase revenue by at least 7%** in the next quarter.

## Data Analysis Using SQL
Below are some of the key SQL queries used in the project:

### Show all customer records:
```sql
SELECT * FROM customers;
```

### Show total number of customers:
```sql
SELECT count(*) FROM customers;
```

### Show transactions for Chennai market (Market Code: Mark001):
```sql
SELECT * FROM transactions WHERE market_code='Mark001';
```

### Show distinct product codes sold in Chennai:
```sql
SELECT DISTINCT product_code FROM transactions WHERE market_code='Mark001';
```

### Show transactions where currency is US dollars:
```sql
SELECT * FROM transactions WHERE currency='USD';
```

### Show transactions in 2020 (Joined with Date Table):
```sql
SELECT transactions.*, date.* 
FROM transactions 
INNER JOIN date ON transactions.order_date=date.date 
WHERE date.year=2020;
```

### Show total revenue in the year 2020:
```sql
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date ON transactions.order_date=date.date 
WHERE date.year=2020 AND (transactions.currency='INR' OR transactions.currency='USD');
```

### Show total revenue in January 2020:
```sql
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date ON transactions.order_date=date.date 
WHERE date.year=2020 AND date.month_name='January' 
AND (transactions.currency='INR' OR transactions.currency='USD');
```

### Show total revenue in Chennai in 2020:
```sql
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date ON transactions.order_date=date.date 
WHERE date.year=2020 AND transactions.market_code='Mark001';
```

## Power BI Implementation
- **Data Cleaning & Transformation**: Performed using **Power Query**
- **Data Modeling**: Established relationships between different tables
- **Measure Creation**: Utilized **DAX** to create meaningful KPIs
- **Dashboard Development**: Designed an **interactive sales performance dashboard**

## Acknowledgment
This project was completed **under the guidance of Codebasics**.

---
✅ **Technologies Used**: Power BI, SQL, Power Query, DAX

📊 **Key Learnings**:
- Data cleaning & transformation
- SQL query writing for business insights
- Power BI visualization techniques
- Data modeling best practices
