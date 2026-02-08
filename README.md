# E-Commerce Sales Analysis Using SQL

## 📌 Project Overview
This project analyzes an e-commerce sales database to extract meaningful business insights using **SQL**. The goal was to explore sales performance, customer behavior, employee productivity, product performance, and revenue trends using real-world, scenario-based analytical questions.

The project uses an **ecommerce database** consisting of customers, orders, employees, products, categories, and order details. Advanced SQL techniques such as joins, aggregations, Common Table Expressions (CTEs), and window functions were applied to answer business-critical questions.

---

## 🗄️ Database Setup
```sql
USE ecommerce;
```
## 🗄️ Database Structure

The database consists of the following core tables:

- `employees`
- `customers`
- `orders`
- `orderdetails`
- `products`
- `categories`

### Table Relationships
Relationships are established using primary and foreign keys such as:

- `orders.employeeid`
- `orders.customerid`
- `orderdetails.orderid`
- `orderdetails.productid`
- `products.categoryid`

---

## 🛠️ Project Workflow & Steps

### 1️⃣ Data Exploration & Understanding
- Examined table structures and relationships
- Identified revenue-related fields:
  - `Quantity`
  - `UnitPrice`
  - `Discount`
- Defined a consistent total sales formula used across all queries:

```text
Quantity * UnitPrice * (1 - Discount)
```
## 2️⃣ Sales Performance Analysis

### Total Sales by Employee
- Joined `employees`, `orders`, and `orderdetails`
- Aggregated revenue per employee
- Provided insight into individual employee contribution to total sales

**Insight:** Identifies top-performing sales employees and supports performance-based evaluation.

---

### Employee Sales Ranking
- Used the `RANK()` window function
- Ranked employees based on total revenue generated

**Insight:** Enables fair ranking even when employees have identical sales values.

---

## 3️⃣ Customer Analysis

### Top 5 Customers by Sales
- Calculated total revenue per customer
- Sorted results to identify highest-value customers

**Insight:** Helps identify VIP customers and supports customer retention strategies.

---

### Customers with Multiple Orders on the Same Date
- Grouped orders by customer and order date
- Used `HAVING COUNT(orderid) > 1`

**Insight:** Highlights bulk buyers or frequent purchasers.

---

## 4️⃣ Time-Based Sales Analysis

### Monthly Sales Trend (1997)
- Extracted month names using `MONTHNAME()`
- Filtered results by the year 1997

**Insight:** Reveals seasonal trends and peak sales months.

---

### Year-over-Year Sales Growth
- Built Common Table Expressions (CTEs) to calculate annual sales per product
- Compared current year sales with previous year
- Calculated percentage growth

**Insight:** Identifies growing or declining products over time.

---

## 5️⃣ Product & Category Analysis

### Products by Category with No Sales
- Used `LEFT JOIN` and `IS NULL`
- Identified products that were never sold

**Insight:** Highlights dead stock or products needing promotion or removal.

---

### Average Discount per Product
- Calculated average discount applied per product

**Insight:** Reveals pricing and discounting patterns.

---

### Products Ordered by Each Customer
- Joined customers’ orders with products
- Displayed quantity ordered per product

**Insight:** Useful for recommendation systems and customer profiling.

---

### Products Never Reordered
- Identified products ordered only once

**Insight:** Indicates low repeat demand or one-time purchases.

---

### Most Valuable Product by Revenue (Per Category)
- Used `ROW_NUMBER()` with `PARTITION BY`
- Selected highest-revenue product in each category

**Insight:** Identifies category leaders and best-selling products.

---

## 6️⃣ Order-Level Analysis

### Order Quantity Percentile
- Calculated total quantity per order
- Applied the `PERCENT_RANK()` window function

**Insight:** Helps classify orders as small, medium, or large relative to others.

---

### Complex Order Conditions
- Identified orders that:
  - Have a total value greater than `$100`
  - Contain at least one product with a discount of `5%` or more

**Insight:** Highlights high-value promotional orders and evaluates discount effectiveness.

---

## ✅ Final Results
- Successfully analyzed an e-commerce sales database using SQL
- Answered **15 real-world business questions**
- Demonstrated:
  - Complex joins
  - Aggregations
  - Window functions
  - Common Table Expressions (CTEs)
  - Date-based analysis
- Generated actionable insights across:
  - Sales performance
  - Customer behavior
  - Product effectiveness
  - Revenue growth trends

---

## 🧠 Key Insights
- A small group of customers and employees contribute disproportionately to total revenue
- Certain products and categories dominate overall sales
- Some products generate revenue only once and are never reordered
- Seasonal patterns significantly impact monthly sales
- Discounts influence high-value orders but must be strategically applied

---

## 🛠️ Technologies Used
- SQL (MySQL / ANSI SQL)
- Window Functions
- Common Table Expressions (CTEs)
- Relational Database Concepts

---

## 🚀 Conclusion
This project demonstrates a **complete SQL analytics workflow**, from database exploration to advanced business insights. It mirrors real-world data analysis tasks performed by data analysts and showcases the ability to transform raw transactional data into meaningful, decision-driving insights.
