# Task-6--Sales-Trend-Analysis-Using-Aggregations

# 📊 Sales Trend Analysis Using SQL Aggregations

**Task 6** of my **Data Analyst Internship**, focused on analyzing monthly revenue and order volume using SQL queries.

---

## 🎯 Objective

- Analyze sales trends over time using aggregation techniques.
- Calculate monthly revenue and total order volume.
- Practice SQL GROUP BY, SUM, COUNT, EXTRACT, and sorting methods.

---

## 🧰 Tools Used

- SQL (PostgreSQL / MySQL compatible)
- Sample table: `online_sales`
- Columns: `order_date`, `amount`, `product_id`, `order_id`

---

## 🗃️ Dataset Assumption

We use a table `online_sales` with the following schema:

| order_id | order_date | amount | product_id |
|----------|------------|--------|------------|
| 1001     | 2022-01-15 | 250.00 | P101       |
| 1002     | 2022-01-20 | 180.00 | P105       |
| ...      | ...        | ...    | ...        |

---

## 🧠 SQL Concepts Practiced

- `EXTRACT(MONTH FROM order_date)` and `EXTRACT(YEAR FROM order_date)`
- `GROUP BY` year and month
- Aggregation with `SUM()` and `COUNT(DISTINCT order_id)`
- Sorting using `ORDER BY`
- Limiting using `LIMIT`

---

## 🧾 SQL Script

```sql
-- Sales Trend Analysis: Monthly Revenue and Order Volume

SELECT
  EXTRACT(YEAR FROM order_date) AS year,
  EXTRACT(MONTH FROM order_date) AS month,
  SUM(amount) AS monthly_revenue,
  COUNT(DISTINCT order_id) AS total_orders
FROM online_sales
GROUP BY year, month
ORDER BY year, month;
