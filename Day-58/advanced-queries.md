-- Day 58: Advanced E-Commerce Queries

USE ecommerce_db;

-- 1. Find products above average price
SELECT *
FROM products
WHERE price > (
    SELECT AVG(price)
    FROM products
);

-- 2. Find the second highest product price
SELECT MAX(price) AS second_highest_price
FROM products
WHERE price < (
    SELECT MAX(price)
    FROM products
);

-- 3. Find customers who placed orders
SELECT *
FROM customers
WHERE customer_id IN (
    SELECT customer_id
    FROM orders
);

-- 4. Find products that have never been ordered
SELECT *
FROM products
WHERE product_id NOT IN (
    SELECT product_id
    FROM order_items
);

-- 5. Find customers with more than one order
SELECT
    c.customer_name,
    COUNT(o.order_id) AS total_orders
FROM customers c
JOIN orders o
ON c.customer_id = o.customer_id
GROUP BY c.customer_id, c.customer_name
HAVING COUNT(o.order_id) > 1;

-- 6. Find the most expensive product in each category
SELECT
    product_name,
    category_id,
    price
FROM (
    SELECT
        product_name,
        category_id,
        price,
        RANK() OVER (
            PARTITION BY category_id
            ORDER BY price DESC
        ) AS product_rank
    FROM products
) ranked_products
WHERE product_rank = 1;

-- 7. Rank products by price
SELECT
    product_name,
    price,
    RANK() OVER (
        ORDER BY price DESC
    ) AS price_rank
FROM products;

-- 8. Assign row numbers to products
SELECT
    product_name,
    price,
    ROW_NUMBER() OVER (
        ORDER BY price DESC
    ) AS row_num
FROM products;

-- 9. Calculate running total of product sales
SELECT
    order_id,
    order_item_id,
    quantity * unit_price AS item_total,
    SUM(quantity * unit_price) OVER (
        ORDER BY order_id, order_item_id
    ) AS running_total
FROM order_items;

-- 10. Use CASE to classify products by price
SELECT
    product_name,
    price,
    CASE
        WHEN price >= 30000 THEN 'Expensive'
        WHEN price >= 5000 THEN 'Medium'
        ELSE 'Affordable'
    END AS price_category
FROM products;

-- 11. Find order totals using a CTE
WITH order_totals AS (
    SELECT
        order_id,
        SUM(quantity * unit_price) AS total_amount
    FROM order_items
    GROUP BY order_id
)
SELECT *
FROM order_totals
WHERE total_amount > 2000;

-- 12. Find customers with total spending above 10000
WITH customer_spending AS (
    SELECT
        c.customer_id,
        c.customer_name,
        SUM(oi.quantity * oi.unit_price) AS total_spending
    FROM customers c
    JOIN orders o
        ON c.customer_id = o.customer_id
    JOIN order_items oi
        ON o.order_id = oi.order_id
    WHERE o.status = 'Completed'
    GROUP BY c.customer_id, c.customer_name
)
SELECT *
FROM customer_spending
WHERE total_spending > 10000;

-- 13. Find the top 3 products by quantity sold
SELECT
    p.product_name,
    SUM(oi.quantity) AS total_sold
FROM products p
JOIN order_items oi
ON p.product_id = oi.product_id
GROUP BY p.product_id, p.product_name
ORDER BY total_sold DESC
LIMIT 3;

-- 14. Find average order value
SELECT
    AVG(order_total) AS average_order_value
FROM (
    SELECT
        o.order_id,
        SUM(oi.quantity * oi.unit_price) AS order_total
    FROM orders o
    JOIN order_items oi
        ON o.order_id = oi.order_id
    WHERE o.status = 'Completed'
    GROUP BY o.order_id
) AS order_summary;

-- 15. Find total completed orders
SELECT COUNT(*) AS completed_orders
FROM orders
WHERE status = 'Completed';