-- Day 61: Transaction Commands

USE ecommerce_db;

-- Check storage engine
SHOW TABLE STATUS
WHERE Name IN ('products', 'customers');

-- Check product records
SELECT * FROM products;

-- Check customer records
SELECT * FROM customers;

-- Start transaction
START TRANSACTION;

-- Update product stock
UPDATE products
SET stock = stock + 5
WHERE product_id = 1;

-- Check updated record
SELECT * FROM products
WHERE product_id = 1;

-- Commit changes
COMMIT;


-- Rollback example
START TRANSACTION;

UPDATE products
SET stock = stock - 10
WHERE product_id = 2;

-- Undo changes
ROLLBACK;


-- Savepoint example
START TRANSACTION;

UPDATE products
SET stock = stock + 2
WHERE product_id = 1;

SAVEPOINT sp1;

UPDATE products
SET stock = stock + 3
WHERE product_id = 2;

ROLLBACK TO SAVEPOINT sp1;

COMMIT;


-- Check transaction isolation
SELECT @@transaction_isolation;

-- Check autocommit setting
SELECT @@autocommit;

-- Check MySQL version
SELECT VERSION();