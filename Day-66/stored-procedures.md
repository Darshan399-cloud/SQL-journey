# Advanced SQL Stored Procedures

## 1. What is a Stored Procedure?

A Stored Procedure is a group of SQL statements stored inside a database.

We can execute it whenever required using the CALL statement.

## 2. Basic Syntax

DELIMITER //

CREATE PROCEDURE procedure_name()
BEGIN
    SQL statements;
END //

DELIMITER ;

## 3. Calling a Procedure

CALL procedure_name();

## 4. Procedure with IN Parameter

IN parameter is used to pass a value into a procedure.

Example:

DELIMITER //

CREATE PROCEDURE get_customer(IN cust_id INT)
BEGIN
    SELECT *
    FROM customers
    WHERE customer_id = cust_id;
END //

DELIMITER ;

Call:

CALL get_customer(1);

## 5. IF-ELSE Condition

IF-ELSE is used to execute different statements based on a condition.

Example:

DELIMITER //

CREATE PROCEDURE check_stock(IN product_id_input INT)
BEGIN
    DECLARE available_stock INT;

    SELECT stock INTO available_stock
    FROM products
    WHERE product_id = product_id_input;

    IF available_stock > 0 THEN
        SELECT 'Product Available' AS message;
    ELSE
        SELECT 'Product Out of Stock' AS message;
    END IF;
END //

DELIMITER ;

Call:

CALL check_stock(1);

## 6. WHILE Loop

A WHILE loop executes statements repeatedly while a condition is true.

Example:

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

Call:

CALL count_numbers();

## 7. Error Handling

Error handling allows us to manage errors inside a stored procedure.

Example:

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

Call:

CALL divide_numbers(10, 2);

## 8. Advantages

1. SQL code can be reused.
2. Reduces repeated queries.
3. Improves code organization.
4. Supports parameters.
5. Supports conditions and loops.
6. Helps manage database operations.
7. Can improve security through controlled access.