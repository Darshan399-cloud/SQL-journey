-- Day 63: Database Backup and Restore

-- 1. Display all databases
SHOW DATABASES;

-- 2. Select E-Commerce database
USE ecommerce_db;

-- 3. Display all tables
SHOW TABLES;

-- 4. Check customer records
SELECT * FROM customers;

-- 5. Check product records
SELECT * FROM products;

-- 6. Create a backup database
CREATE DATABASE ecommerce_backup_test;

-- 7. Copy customer table structure
CREATE TABLE ecommerce_backup_test.customers
LIKE ecommerce_db.customers;

-- 8. Copy customer table data
INSERT INTO ecommerce_backup_test.customers
SELECT * FROM ecommerce_db.customers;

-- 9. Verify copied records
SELECT *
FROM ecommerce_backup_test.customers;

-- 10. Count original customer records
SELECT COUNT(*) AS original_count
FROM ecommerce_db.customers;

-- 11. Count backup customer records
SELECT COUNT(*) AS backup_count
FROM ecommerce_backup_test.customers;

-- 12. Delete test backup database
-- Run only after completing the practice.
-- DROP DATABASE ecommerce_backup_test;