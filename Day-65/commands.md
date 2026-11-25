# Day 65 - SQL Views Commands

## Database

USE ecommerce_db;

## 1. Create a Simple View

CREATE VIEW customer_view AS
SELECT customer_id, customer_name, city
FROM customers;

## 2. Display View Data

SELECT * FROM customer_view;

## 3. Create View with WHERE Condition

CREATE VIEW pune_customers AS
SELECT customer_id, customer_name, city
FROM customers
WHERE city = 'Pune';

## 4. Create View Using JOIN

CREATE VIEW order_details_view AS
SELECT
    o.order_id,
    c.customer_name,
    o.order_date,
    o.status
FROM orders o
JOIN customers c
ON o.customer_id = c.customer_id;

## 5. Display View

SELECT * FROM order_details_view;

## 6. Show All Views

SHOW FULL TABLES
WHERE Table_type = 'VIEW';

## 7. View Definition

SHOW CREATE VIEW customer_view;

## 8. Update an Updatable View

UPDATE customer_view
SET city = 'Pune'
WHERE customer_id = 1;

## 9. Drop a View

DROP VIEW IF EXISTS pune_customers;

## 10. Create a Summary Table

CREATE TABLE order_sales_summary AS
SELECT
    order_id,
    SUM(quantity * unit_price) AS total_amount
FROM order_items
GROUP BY order_id;

## 11. Display Summary

SELECT * FROM order_sales_summary;

## 12. Refresh Summary Table

TRUNCATE TABLE order_sales_summary;

INSERT INTO order_sales_summary
SELECT
    order_id,
    SUM(quantity * unit_price)
FROM order_items
GROUP BY order_id;

## 13. Drop Summary Table

DROP TABLE IF EXISTS order_sales_summary;