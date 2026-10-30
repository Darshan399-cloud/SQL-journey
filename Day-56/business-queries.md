# SQL Business Queries

## 1. Calculate Total Sales

SELECT SUM(amount) AS total_sales
FROM orders;

## 2. Find Total Orders

SELECT COUNT(*) AS total_orders
FROM orders;

## 3. Find Average Order Amount

SELECT AVG(amount) AS average_order
FROM orders;

## 4. Find the Highest Order Amount

SELECT MAX(amount) AS highest_order
FROM orders;

## 5. Find Customer-Wise Total Orders

SELECT customer_id, COUNT(*) AS total_orders
FROM orders
GROUP BY customer_id;

## 6. Find Customers Who Have Placed Orders

SELECT c.customer_id, c.customer_name
FROM customers c
INNER JOIN orders o
ON c.customer_id = o.customer_id
GROUP BY c.customer_id, c.customer_name;

## 7. Find Customers Who Have Not Placed Orders

SELECT c.*
FROM customers c
LEFT JOIN orders o
ON c.customer_id = o.customer_id
WHERE o.order_id IS NULL;

## 8. Find Customers Spending More Than 10000

SELECT customer_id, SUM(amount) AS total_spending
FROM orders
GROUP BY customer_id
HAVING SUM(amount) > 10000;

## 9. Find Monthly Sales

SELECT
    YEAR(order_date) AS sales_year,
    MONTH(order_date) AS sales_month,
    SUM(amount) AS total_sales
FROM orders
GROUP BY YEAR(order_date), MONTH(order_date)
ORDER BY sales_year, sales_month;

## 10. Find the Top Three Customers by Spending

SELECT customer_id, SUM(amount) AS total_spending
FROM orders
GROUP BY customer_id
ORDER BY total_spending DESC
LIMIT 3;