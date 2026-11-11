-- Day 59: SQL Views

USE ecommerce_db;

-- 1. Create a view for all customers
CREATE VIEW customer_view AS
SELECT
    customer_id,
    customer_name,
    email,
    city
FROM customers;

-- Display view
SELECT * FROM customer_view;


-- 2. Create a view for available products
CREATE VIEW available_products AS
SELECT
    product_id,
    product_name,
    price,
    stock
FROM products
WHERE stock > 0;

SELECT * FROM available_products;


-- 3. Create a view for product categories
CREATE VIEW product_category_view AS
SELECT
    p.product_name,
    c.category_name,
    p.price
FROM products p
JOIN categories c
    ON p.category_id = c.category_id;

SELECT * FROM product_category_view;


-- 4. Create a view for customer orders
CREATE VIEW customer_orders_view AS
SELECT
    c.customer_name,
    o.order_id,
    o.order_date,
    o.status
FROM customers c
JOIN orders o
    ON c.customer_id = o.customer_id;

SELECT * FROM customer_orders_view;


-- 5. Create a view for order totals
CREATE VIEW order_totals_view AS
SELECT
    o.order_id,
    o.customer_id,
    o.order_date,
    o.status,
    SUM(oi.quantity * oi.unit_price) AS total_amount
FROM orders o
JOIN order_items oi
    ON o.order_id = oi.order_id
GROUP BY
    o.order_id,
    o.customer_id,
    o.order_date,
    o.status;

SELECT * FROM order_totals_view;


-- 6. Create a view for completed orders
CREATE VIEW completed_orders_view AS
SELECT
    order_id,
    customer_id,
    order_date,
    status
FROM orders
WHERE status = 'Completed';

SELECT * FROM completed_orders_view;


-- 7. Create a view for low-stock products
CREATE VIEW low_stock_products AS
SELECT
    product_id,
    product_name,
    stock
FROM products
WHERE stock < 10;

SELECT * FROM low_stock_products;


-- 8. Create or replace a view
CREATE OR REPLACE VIEW customer_view AS
SELECT
    customer_id,
    customer_name,
    city
FROM customers;

SELECT * FROM customer_view;


-- 9. Display all views
SHOW FULL TABLES
WHERE Table_type = 'VIEW';


-- 10. Delete a view
-- Run only when you want to remove it.

-- DROP VIEW customer_view;