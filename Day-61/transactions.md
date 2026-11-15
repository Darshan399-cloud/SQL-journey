-- Day 61: SQL Transactions

USE ecommerce_db;

-- 1. Start a transaction
START TRANSACTION;

-- Update product stock
UPDATE products
SET stock = stock - 2
WHERE product_id = 1;

-- Check updated stock
SELECT * FROM products
WHERE product_id = 1;

-- Save changes permanently
COMMIT;


-- 2. ROLLBACK Example
-- Rollback cancels uncommitted changes.

START TRANSACTION;

UPDATE products
SET stock = stock - 5
WHERE product_id = 2;

-- Check temporary changes
SELECT * FROM products
WHERE product_id = 2;

-- Cancel the changes
ROLLBACK;

-- Check stock after rollback
SELECT * FROM products
WHERE product_id = 2;


-- 3. SAVEPOINT Example

START TRANSACTION;

UPDATE products
SET stock = stock - 1
WHERE product_id = 1;

SAVEPOINT first_update;

UPDATE products
SET stock = stock - 2
WHERE product_id = 2;

SAVEPOINT second_update;

UPDATE products
SET stock = stock - 3
WHERE product_id = 3;

-- Rollback only the third update
ROLLBACK TO SAVEPOINT second_update;

-- Save the remaining changes
COMMIT;


-- 4. Release a Savepoint

START TRANSACTION;

UPDATE products
SET stock = stock + 1
WHERE product_id = 1;

SAVEPOINT stock_update;

UPDATE products
SET stock = stock + 1
WHERE product_id = 2;

RELEASE SAVEPOINT stock_update;

COMMIT;


-- 5. Transaction with Multiple Updates

START TRANSACTION;

UPDATE products
SET stock = stock - 1
WHERE product_id = 1;

UPDATE products
SET stock = stock + 1
WHERE product_id = 2;

COMMIT;


-- 6. Transaction with INSERT

START TRANSACTION;

INSERT INTO customers
(customer_name, email, city)
VALUES
('Transaction User', 'transaction@gmail.com', 'Pune');

-- Save the new customer
COMMIT;

-- Check inserted customer
SELECT *
FROM customers
WHERE email = 'transaction@gmail.com';


-- 7. Transaction with DELETE

START TRANSACTION;

DELETE FROM customers
WHERE email = 'transaction@gmail.com';

-- Cancel deletion
ROLLBACK;

-- Check customer record
SELECT *
FROM customers
WHERE email = 'transaction@gmail.com';


-- 8. Check transaction isolation level
SELECT @@transaction_isolation;