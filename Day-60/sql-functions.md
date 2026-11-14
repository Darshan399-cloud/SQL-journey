-- Day 60: SQL User-Defined Functions

USE ecommerce_db;

-- 1. Function to calculate product discount

DELIMITER //

CREATE FUNCTION CalculateDiscount(
    p_price DECIMAL(10,2),
    p_discount DECIMAL(5,2)
)
RETURNS DECIMAL(10,2)
DETERMINISTIC
NO SQL
BEGIN
    RETURN p_price - (p_price * p_discount / 100);
END //

DELIMITER ;

-- Test function
SELECT CalculateDiscount(1000, 10) AS final_price;


-- 2. Function to calculate total order amount

DELIMITER //

CREATE FUNCTION GetOrderAmount(
    p_order_id INT
)
RETURNS DECIMAL(12,2)
READS SQL DATA
BEGIN
    DECLARE total_amount DECIMAL(12,2);

    SELECT COALESCE(
        SUM(quantity * unit_price), 0
    )
    INTO total_amount
    FROM order_items
    WHERE order_id = p_order_id;

    RETURN total_amount;
END //

DELIMITER ;

-- Test function
SELECT GetOrderAmount(1) AS order_total;


-- 3. Function to classify product price

DELIMITER //

CREATE FUNCTION GetPriceCategory(
    p_price DECIMAL(10,2)
)
RETURNS VARCHAR(20)
DETERMINISTIC
NO SQL
BEGIN
    DECLARE category_name VARCHAR(20);

    IF p_price >= 30000 THEN
        SET category_name = 'Expensive';
    ELSEIF p_price >= 5000 THEN
        SET category_name = 'Medium';
    ELSE
        SET category_name = 'Affordable';
    END IF;

    RETURN category_name;
END //

DELIMITER ;

-- Test function
SELECT
    product_name,
    price,
    GetPriceCategory(price) AS price_category
FROM products;


-- 4. Function to calculate GST amount

DELIMITER //

CREATE FUNCTION CalculateGST(
    p_amount DECIMAL(10,2),
    p_gst_rate DECIMAL(5,2)
)
RETURNS DECIMAL(10,2)
DETERMINISTIC
NO SQL
BEGIN
    RETURN p_amount * p_gst_rate / 100;
END //

DELIMITER ;

-- Test function
SELECT CalculateGST(1000, 18) AS gst_amount;


-- 5. Function to calculate final amount with GST

DELIMITER //

CREATE FUNCTION FinalAmountWithGST(
    p_amount DECIMAL(10,2),
    p_gst_rate DECIMAL(5,2)
)
RETURNS DECIMAL(10,2)
DETERMINISTIC
NO SQL
BEGIN
    RETURN p_amount + (p_amount * p_gst_rate / 100);
END //

DELIMITER ;

-- Test function
SELECT FinalAmountWithGST(1000, 18) AS final_amount;


-- 6. Use functions with products
SELECT
    product_name,
    price,
    CalculateDiscount(price, 10) AS discounted_price,
    GetPriceCategory(price) AS price_category
FROM products;


-- 7. Display all functions
SHOW FUNCTION STATUS
WHERE Db = 'ecommerce_db';


-- 8. Delete a function
-- Run only when you want to remove it.

-- DROP FUNCTION CalculateDiscount;