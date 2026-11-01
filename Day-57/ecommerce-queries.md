-- Day 57: SQL E-Commerce Database Project

-- 1. Display all customers
SELECT * FROM customers;

-- 2. Display all products
SELECT * FROM products;

-- 3. Display products with category names
SELECT
    p.product_name,
    c.category_name,
    p.price
FROM products p
JOIN categories c
ON p.category_id = c.category_id;

-- 4. Display all customer orders
SELECT
    c.customer_name,
    o.order_id,
    o.order_date,
    o.status
FROM customers c
JOIN orders o
ON c.customer_id = o.customer_id;

-- 5. Calculate total amount of each order
SELECT
    order_id,
    SUM(quantity * unit_price) AS order_total
FROM order_items
GROUP BY order_id;

-- 6. Display customer-wise order totals
SELECT
    c.customer_name,
    o.order_id,
    SUM(oi.quantity * oi.unit_price) AS order_total
FROM customers c
JOIN orders o
ON c.customer_id = o.customer_id
JOIN order_items oi
ON o.order_id = oi.order_id
GROUP BY c.customer_name, o.order_id;

-- 7. Find total sales
SELECT
    SUM(quantity * unit_price) AS total_sales
FROM order_items;

-- 8. Find total number of orders
SELECT COUNT(*) AS total_orders
FROM orders;

-- 9. Find products with price greater than 1000
SELECT *
FROM products
WHERE price > 1000;

-- 10. Find products with stock less than 10
SELECT *
FROM products
WHERE stock < 10;

-- 11. Find customers who have placed orders
SELECT DISTINCT
    c.customer_name
FROM customers c
JOIN orders o
ON c.customer_id = o.customer_id;

-- 12. Find customers who have not placed orders
SELECT
    c.customer_name
FROM customers c
LEFT JOIN orders o
ON c.customer_id = o.customer_id
WHERE o.order_id IS NULL;

-- 13. Find the most expensive product
SELECT *
FROM products
ORDER BY price DESC
LIMIT 1;

-- 14. Find category-wise product count
SELECT
    c.category_name,
    COUNT(p.product_id) AS total_products
FROM categories c
LEFT JOIN products p
ON c.category_id = p.category_id
GROUP BY c.category_id, c.category_name;

-- 15. Find orders with total amount greater than 2000
SELECT
    order_id,
    SUM(quantity * unit_price) AS order_total
FROM order_items
GROUP BY order_id
HAVING SUM(quantity * unit_price) > 2000;

-- 16. Find completed orders
SELECT *
FROM orders
WHERE status = 'Completed';

-- 17. Find total payment received
SELECT
    SUM(amount) AS total_payment
FROM payments
WHERE payment_status = 'Paid';

-- 18. Display order and payment details
SELECT
    o.order_id,
    o.status,
    p.amount,
    p.payment_status
FROM orders o
LEFT JOIN payments p
ON o.order_id = p.order_id;

-- 19. Find the top-selling products by quantity
SELECT
    p.product_name,
    SUM(oi.quantity) AS total_sold
FROM products p
JOIN order_items oi
ON p.product_id = oi.product_id
GROUP BY p.product_id, p.product_name
ORDER BY total_sold DESC;

-- 20. Find total sales by product category
SELECT
    c.category_name,
    SUM(oi.quantity * oi.unit_price) AS category_sales
FROM categories c
JOIN products p
ON c.category_id = p.category_id
JOIN order_items oi
ON p.product_id = oi.product_id
GROUP BY c.category_id, c.category_name;