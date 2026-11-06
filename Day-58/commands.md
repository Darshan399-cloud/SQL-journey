-- Select existing Day 57 database
USE ecommerce_db;

-- Check all tables
SHOW TABLES;

-- Check table structures
DESCRIBE customers;
DESCRIBE categories;
DESCRIBE products;
DESCRIBE orders;
DESCRIBE order_items;
DESCRIBE payments;

-- Check existing records
SELECT * FROM customers;
SELECT * FROM categories;
SELECT * FROM products;
SELECT * FROM orders;
SELECT * FROM order_items;
SELECT * FROM payments;

-- Check MySQL version
SELECT VERSION();

-- Test CTE
WITH product_count AS (
    SELECT COUNT(*) AS total_products
    FROM products
)
SELECT * FROM product_count;

-- Test window function
SELECT
    product_name,
    price,
    DENSE_RANK() OVER (ORDER BY price DESC) AS price_rank
FROM products;