# SQL Stored Procedures

A Stored Procedure is a group of SQL statements stored in the database and executed when needed.

Stored Procedures are useful for storing reusable SQL logic.

## Basic Syntax

DELIMITER //

CREATE PROCEDURE procedure_name()
BEGIN
    SQL statements;
END //

DELIMITER ;

## Example

DELIMITER //

CREATE PROCEDURE get_employees()
BEGIN
    SELECT *
    FROM employees;
END //

DELIMITER ;

## Execute Procedure

CALL get_employees();

## Procedure with WHERE

DELIMITER //

CREATE PROCEDURE get_it_employees()
BEGIN
    SELECT *
    FROM employees
    WHERE department = 'IT';
END //

DELIMITER ;

## Execute

CALL get_it_employees();

## Drop Procedure

DROP PROCEDURE get_employees;

## Advantages

- Reusable SQL logic
- Reduces repeated queries
- Can improve code organization
- Business logic can be stored in the database
- Can accept parameters