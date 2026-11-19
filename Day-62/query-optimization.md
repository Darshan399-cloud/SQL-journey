-- Day 62: SQL Query Optimization

USE ecommerce_db;

-- 1. Check query execution plan
EXPLAIN
SELECT *
FROM products
WHERE product_name = 'Laptop';


-- 2. Check query execution plan for customer search
EXPLAIN
SELECT *
FROM customers
WHERE city = 'Pune';


-- 3. Select only required columns
-- Less efficient approach
SELECT *
FROM products
WHERE category_id = 1;

-- Better approach
SELECT product_name, price
FROM products
WHERE category_id = 1;


-- 4. Avoid unnecessary functions on indexed columns
-- This can prevent efficient index usage
SELECT *
FROM products
WHERE UPPER(product_name) = 'LAPTOP';

-- Better approach
SELECT *
FROM products
WHERE product_name = 'Laptop';


-- 5. Use LIMIT to restrict returned rows
SELECT *
FROM products
ORDER BY price DESC
LIMIT 3;


-- 6. Optimize JOIN query
SELECT
    c.customer_name,
    o.order_id,
    o.status
FROM customers c
JOIN orders o
ON c.customer_id = o.customer_id
WHERE o.status = 'Completed';


-- 7. Analyze a query using EXPLAIN
EXPLAIN
SELECT
    p.product_name,
    c.category_name
FROM products p
JOIN categories c
ON p.category_id = c.category_id;


-- 8. Check query execution details
EXPLAIN FORMAT=JSON
SELECT *
FROM orders
WHERE customer_id = 1;


-- 9. Create an index for order customer search
CREATE INDEX idx_orders_customer
ON orders(customer_id);

-- Check execution plan again
EXPLAIN
SELECT *
FROM orders
WHERE customer_id = 1;


-- 10. Analyze table statistics
ANALYZE TABLE products;
ANALYZE TABLE customers;
ANALYZE TABLE orders;