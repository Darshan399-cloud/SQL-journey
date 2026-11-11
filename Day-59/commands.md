-- Select database
USE ecommerce_db;

-- Check existing tables
SHOW TABLES;

-- Check stored procedures
SHOW PROCEDURE STATUS
WHERE Db = 'ecommerce_db';

-- Check all views
SHOW FULL TABLES
WHERE Table_type = 'VIEW';

-- Display procedure definition
SHOW CREATE PROCEDURE GetAllCustomers;

-- Display view definition
SHOW CREATE VIEW customer_view;

-- Execute a procedure
CALL GetAllCustomers();

-- Execute procedure with parameter
CALL GetCustomerById(1);

-- Execute procedure with OUT parameter
CALL GetTotalCustomers(@total);
SELECT @total;

-- Display view data
SELECT * FROM customer_view;

-- Display product view
SELECT * FROM available_products;

-- Display order totals
SELECT * FROM order_totals_view;

-- Drop procedure example
-- DROP PROCEDURE GetAllCustomers;

-- Drop view example
-- DROP VIEW customer_view;