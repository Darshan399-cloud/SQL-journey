-- Day 62: Index and Optimization Commands

USE ecommerce_db;

-- Display all tables
SHOW TABLES;

-- Display products table structure
DESCRIBE products;

-- Display customer table structure
DESCRIBE customers;

-- Display all product indexes
SHOW INDEX FROM products;

-- Display all customer indexes
SHOW INDEX FROM customers;

-- Create a simple index
CREATE INDEX idx_order_status
ON orders(status);

-- Check the created index
SHOW INDEX FROM orders;

-- Use EXPLAIN
EXPLAIN
SELECT *
FROM orders
WHERE status = 'Completed';

-- Analyze table
ANALYZE TABLE orders;

-- Check query execution plan in JSON format
EXPLAIN FORMAT=JSON
SELECT *
FROM products
WHERE price > 1000;

-- Drop an index
DROP INDEX idx_order_status
ON orders;

-- Verify index deletion
SHOW INDEX FROM orders;