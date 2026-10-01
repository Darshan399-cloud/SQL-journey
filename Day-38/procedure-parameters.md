# Stored Procedure Parameters

Parameters allow us to pass values to a Stored Procedure.

## IN Parameter

IN parameter is used to pass a value into a procedure.

## Syntax

DELIMITER //

CREATE PROCEDURE get_employee_by_department(
    IN dept_name VARCHAR(100)
)
BEGIN
    SELECT *
    FROM employees
    WHERE department = dept_name;
END //

DELIMITER ;

## Execute

CALL get_employee_by_department('IT');

## Procedure with Salary

DELIMITER //

CREATE PROCEDURE get_employees_by_salary(
    IN min_salary DECIMAL(10,2)
)
BEGIN
    SELECT *
    FROM employees
    WHERE salary >= min_salary;
END //

DELIMITER ;

## Execute

CALL get_employees_by_salary(60000);

## OUT Parameter

OUT parameter is used to return a value from a procedure.

Example:

DELIMITER //

CREATE PROCEDURE count_employees(
    OUT total_employees INT
)
BEGIN
    SELECT COUNT(*)
    INTO total_employees
    FROM employees;
END //

DELIMITER ;

## Execute OUT Procedure

CALL count_employees(@total);

SELECT @total;

## Important

IN is used to send a value into a procedure.

OUT is used to return a value from a procedure.