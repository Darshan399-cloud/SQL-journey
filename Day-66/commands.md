# Day 66 - SQL Stored Procedures Commands

USE ecommerce_db;

## 1. Create Procedure with IN Parameter

DELIMITER //

CREATE PROCEDURE get_customer(IN cust_id INT)
BEGIN
    SELECT *
    FROM customers
    WHERE customer_id = cust_id;
END //

DELIMITER ;

CALL get_customer(1);

## 2. Create Procedure with OUT Parameter

DELIMITER //

CREATE PROCEDURE get_total_customers(OUT total INT)
BEGIN
    SELECT COUNT(*)
    INTO total
    FROM customers;
END //

DELIMITER ;

CALL get_total_customers(@result);

SELECT @result;

## 3. Create Procedure with INOUT Parameter

DELIMITER //

CREATE PROCEDURE increase_number(INOUT num INT)
BEGIN
    SET num = num + 10;
END //

DELIMITER ;

SET @value = 20;

CALL increase_number(@value);

SELECT @value;

## 4. Create Procedure with IF-ELSE

DELIMITER //

CREATE PROCEDURE check_stock(IN product_id_input INT)
BEGIN
    DECLARE available_stock INT DEFAULT NULL;

    SELECT stock
    INTO available_stock
    FROM products
    WHERE product_id = product_id_input;

    IF available_stock IS NULL THEN
        SELECT 'Product Not Found' AS message;
    ELSEIF available_stock > 0 THEN
        SELECT 'Product Available' AS message;
    ELSE
        SELECT 'Product Out of Stock' AS message;
    END IF;
END //

DELIMITER ;

CALL check_stock(1);

## 5. Create Procedure with WHILE Loop

DELIMITER //

CREATE PROCEDURE count_numbers()
BEGIN
    DECLARE counter INT DEFAULT 1;

    WHILE counter <= 5 DO
        SELECT counter;
        SET counter = counter + 1;
    END WHILE;
END //

DELIMITER ;

CALL count_numbers();

## 6. Create Procedure with Error Handler

DELIMITER //

CREATE PROCEDURE divide_numbers(
    IN num1 DECIMAL(10,2),
    IN num2 DECIMAL(10,2)
)
BEGIN
    DECLARE EXIT HANDLER FOR SQLEXCEPTION
    BEGIN
        SELECT 'An SQL error occurred' AS message;
    END;

    IF num2 = 0 THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'Division by zero is not allowed';
    ELSE
        SELECT num1 / num2 AS result;
    END IF;
END //

DELIMITER ;

CALL divide_numbers(10, 2);

## 7. Show Stored Procedures

SHOW PROCEDURE STATUS
WHERE Db = 'ecommerce_db';

## 8. Show Procedure Definition

SHOW CREATE PROCEDURE get_customer;

## 9. Delete a Procedure

DROP PROCEDURE IF EXISTS get_customer;