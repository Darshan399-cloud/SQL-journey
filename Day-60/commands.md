-- Select database
USE ecommerce_db;

-- Check database tables
SHOW TABLES;

-- Check existing triggers
SHOW TRIGGERS;

-- Check existing functions
SHOW FUNCTION STATUS
WHERE Db = 'ecommerce_db';

-- Check product price history
SELECT * FROM product_price_history;

-- Check order audit records
SELECT * FROM order_audit;

-- Test discount function
SELECT CalculateDiscount(2000, 15);

-- Test GST function
SELECT CalculateGST(5000, 18);

-- Test order amount function
SELECT GetOrderAmount(1);

-- Test price category function
SELECT GetPriceCategory(55000);

-- Display product information
SELECT * FROM products;

-- Display order information
SELECT * FROM orders;

-- Display order items
SELECT * FROM order_items;

-- Remove trigger example
-- DROP TRIGGER before_product_insert;

-- Remove function example
-- DROP FUNCTION CalculateDiscount;