# SQL Functions

A SQL Function is a database object that accepts input, performs an operation and returns a value.

Functions are useful for reusable calculations and data processing.

## Basic Syntax

DELIMITER //

CREATE FUNCTION function_name(parameter datatype)
RETURNS datatype
DETERMINISTIC
BEGIN
    RETURN value;
END //

DELIMITER ;

## Example

DELIMITER //

CREATE FUNCTION add_numbers(
    a INT,
    b INT
)
RETURNS INT
DETERMINISTIC
BEGIN
    RETURN a + b;
END //

DELIMITER ;

## Call Function

SELECT add_numbers(10, 20);

Result:

30

## Function with Employee Salary

DELIMITER //

CREATE FUNCTION annual_salary(
    monthly_salary DECIMAL(10,2)
)
RETURNS DECIMAL(10,2)
DETERMINISTIC
BEGIN
    RETURN monthly_salary * 12;
END //

DELIMITER ;

## Call Function

SELECT annual_salary(50000);

Result:

600000

## Function with Table Data

SELECT
    name,
    salary,
    annual_salary(salary) AS yearly_salary
FROM employees;

## Drop Function

DROP FUNCTION add_numbers;