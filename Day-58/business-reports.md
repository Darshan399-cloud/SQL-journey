-- Day 58: E-Commerce Business Reports

USE ecommerce_db;

-- 1. Customer-wise completed order report
SELECT
    c.customer_name,
    COUNT(DISTINCT o.order_id) AS total_orders,
    SUM(oi.quantity * oi.unit_price) AS total_spending
FROM customers c
JOIN orders o
    ON c.customer_id = o.customer_id
JOIN order_items oi
    ON o.order_id = oi.order_id
WHERE o.status = 'Completed'
GROUP BY c.customer_id, c.customer_name;

-- 2. Category-wise sales report
SELECT
    cat.category_name,
    SUM(oi.quantity * oi.unit_price) AS total_sales
FROM categories cat
JOIN products p
    ON cat.category_id = p.category_id
JOIN order_items oi
    ON p.product_id = oi.product_id
JOIN orders o
    ON oi.order_id = o.order_id
WHERE o.status = 'Completed'
GROUP BY cat.category_id, cat.category_name;

-- 3. Order status summary
SELECT
    status,
    COUNT(*) AS total_orders
FROM orders
GROUP BY status;

-- 4. Product stock report
SELECT
    product_name,
    stock,
    CASE
        WHEN stock = 0 THEN 'Out of Stock'
        WHEN stock < 10 THEN 'Low Stock'
        ELSE 'Available'
    END AS stock_status
FROM products;

-- 5. Monthly sales report
SELECT
    DATE_FORMAT(o.order_date, '%Y-%m') AS sales_month,
    SUM(oi.quantity * oi.unit_price) AS monthly_sales
FROM orders o
JOIN order_items oi
    ON o.order_id = oi.order_id
WHERE o.status = 'Completed'
GROUP BY DATE_FORMAT(o.order_date, '%Y-%m')
ORDER BY sales_month;

-- 6. Top spending customer
SELECT
    c.customer_name,
    SUM(oi.quantity * oi.unit_price) AS total_spending
FROM customers c
JOIN orders o
    ON c.customer_id = o.customer_id
JOIN order_items oi
    ON o.order_id = oi.order_id
WHERE o.status = 'Completed'
GROUP BY c.customer_id, c.customer_name
ORDER BY total_spending DESC
LIMIT 1;

-- 7. Payment status report
SELECT
    payment_status,
    COUNT(*) AS payment_count,
    SUM(amount) AS total_amount
FROM payments
GROUP BY payment_status;

-- 8. Products with sales and remaining stock
SELECT
    p.product_name,
    p.stock,
    COALESCE(SUM(oi.quantity), 0) AS total_sold
FROM products p
LEFT JOIN order_items oi
    ON p.product_id = oi.product_id
GROUP BY p.product_id, p.product_name, p.stock;

-- 9. Completed order payment summary
SELECT
    o.order_id,
    o.status,
    COALESCE(SUM(
        CASE
            WHEN p.payment_status = 'Paid' THEN p.amount
            ELSE 0
        END
    ), 0) AS amount_paid
FROM orders o
LEFT JOIN payments p
    ON o.order_id = p.order_id
WHERE o.status = 'Completed'
GROUP BY o.order_id, o.status;

-- 10. Daily sales report
SELECT
    o.order_date,
    SUM(oi.quantity * oi.unit_price) AS daily_sales
FROM orders o
JOIN order_items oi
    ON o.order_id = oi.order_id
WHERE o.status = 'Completed'
GROUP BY o.order_date
ORDER BY o.order_date;