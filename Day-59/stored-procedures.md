-- Day 59: SQL Stored Procedures

USE ecommerce_db;

-- 1. Create a procedure to display all customers
DELIMITER //

CREATE PROCEDURE GetAllCustomers()
BEGIN
    SELECT * FROM customers;
END //

DELIMITER ;

-- Execute procedure
CALL GetAllCustomers();


-- 2. Procedure to display all products
DELIMITER //

CREATE PROCEDURE GetAllProducts()
BEGIN
    SELECT * FROM products;
END //

DELIMITER ;

CALL GetAllProducts();


-- 3. Procedure with IN parameter
-- Find customer using customer ID

DELIMITER //

CREATE PROCEDURE GetCustomerById(IN p_customer_id INT)
BEGIN
    SELECT *
    FROM customers
    WHERE customer_id = p_customer_id;
END //

DELIMITER ;

CALL GetCustomerById(1);


-- 4. Procedure to find products by category
DELIMITER //

CREATE PROCEDURE GetProductsByCategory(IN p_category_id INT)
BEGIN
    SELECT
        product_id,
        product_name,
        price,
        stock
    FROM products
    WHERE category_id = p_category_id;
END //

DELIMITER ;

CALL GetProductsByCategory(1);


-- 5. Procedure to calculate order total
DELIMITER //

CREATE PROCEDURE GetOrderTotal(IN p_order_id INT)
BEGIN
    SELECT
        order_id,
        SUM(quantity * unit_price) AS total_amount
    FROM order_items
    WHERE order_id = p_order_id
    GROUP BY order_id;
END //

DELIMITER ;

CALL GetOrderTotal(1);


-- 6. Procedure with OUT parameter
DELIMITER //

CREATE PROCEDURE GetTotalCustomers(OUT p_total INT)
BEGIN
    SELECT COUNT(*)
    INTO p_total
    FROM customers;
END //

DELIMITER ;

CALL GetTotalCustomers(@total);

SELECT @total AS total_customers;


-- 7. Procedure to update product stock
DELIMITER //

CREATE PROCEDURE UpdateProductStock(
    IN p_product_id INT,
    IN p_new_stock INT
)
BEGIN
    UPDATE products
    SET stock = p_new_stock
    WHERE product_id = p_product_id;
END //

DELIMITER ;

CALL UpdateProductStock(1, 20);

SELECT * FROM products WHERE product_id = 1;


-- 8. Procedure to display customer orders
DELIMITER //

CREATE PROCEDURE GetCustomerOrders(IN p_customer_id INT)
BEGIN
    SELECT
        c.customer_name,
        o.order_id,
        o.order_date,
        o.status
    FROM customers c
    JOIN orders o
        ON c.customer_id = o.customer_id
    WHERE c.customer_id = p_customer_id;
END //

DELIMITER ;

CALL GetCustomerOrders(1);


-- 9. View all stored procedures in current database
SHOW PROCEDURE STATUS
WHERE Db = 'ecommerce_db';


-- 10. Delete a stored procedure
-- Run only when you want to remove the procedure.

-- DROP PROCEDURE GetAllCustomers;