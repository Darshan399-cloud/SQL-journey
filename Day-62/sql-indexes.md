-- Day 62: SQL Indexes

USE ecommerce_db;

-- 1. Display all indexes on products table
SHOW INDEX FROM products;

-- 2. Create an index on product_name
CREATE INDEX idx_product_name
ON products(product_name);

-- Search using indexed column
SELECT *
FROM products
WHERE product_name = 'Laptop';


-- 3. Create an index on product price
CREATE INDEX idx_product_price
ON products(price);

-- Search products by price
SELECT *
FROM products
WHERE price > 1000;


-- 4. Create an index on customer city
CREATE INDEX idx_customer_city
ON customers(city);

-- Search customers by city
SELECT *
FROM customers
WHERE city = 'Pune';


-- 5. Create a composite index
CREATE INDEX idx_product_category_price
ON products(category_id, price);

-- Search using composite index
SELECT *
FROM products
WHERE category_id = 1
AND price > 10000;


-- 6. Create a unique index
-- Email is already UNIQUE in the Day 57 table.
-- This example uses a new unique index on order_id and payment_id.
CREATE UNIQUE INDEX idx_payment_order_unique
ON payments(order_id, payment_id);


-- 7. Display indexes
SHOW INDEX FROM customers;
SHOW INDEX FROM products;
SHOW INDEX FROM payments;


-- 8. Drop an index
DROP INDEX idx_product_price
ON products;

-- 9. Check indexes after deletion
SHOW INDEX FROM products;