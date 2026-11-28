# SQL Stored Procedure Parameters

## 1. Types of Parameters

MySQL supports three main parameter types:

1. IN
2. OUT
3. INOUT

## 2. IN Parameter

IN parameter passes a value into a procedure.

Example:

DELIMITER //

CREATE PROCEDURE show_number(IN num INT)
BEGIN
    SELECT num AS number;
END //

DELIMITER ;

Call:

CALL show_number(100);

## 3. OUT Parameter

OUT parameter returns a value from a procedure.

Example:

DELIMITER //

CREATE PROCEDURE get_total_customers(OUT total INT)
BEGIN
    SELECT COUNT(*)
    INTO total
    FROM customers;
END //

DELIMITER ;

Call:

CALL get_total_customers(@result);

SELECT @result AS total_customers;

## 4. INOUT Parameter

INOUT parameter accepts an input value and returns an updated value.

Example:

DELIMITER //

CREATE PROCEDURE increase_number(INOUT num INT)
BEGIN
    SET num = num + 10;
END //

DELIMITER ;

Call:

SET @value = 20;

CALL increase_number(@value);

SELECT @value AS updated_value;

Output:

30

## 5. Difference Between IN, OUT and INOUT

| Parameter | Purpose |
|---|---|
| IN | Passes input value |
| OUT | Returns output value |
| INOUT | Accepts and returns value |

## 6. Important Points

1. IN is the default parameter mode.
2. OUT is used to return values.
3. INOUT is used for both input and output.
4. User variables such as @result can store returned values.
5. Parameters make procedures flexible and reusable.