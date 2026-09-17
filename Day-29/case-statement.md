# SQL CASE Statement

CASE is used to apply conditional logic in SQL.

It works similar to IF-ELSE logic in programming.

## Basic Syntax

SELECT column_name,
CASE
    WHEN condition THEN result
    WHEN condition THEN result
    ELSE result
END AS alias
FROM table_name;

## Example

SELECT
    name,
    salary,
    CASE
        WHEN salary >= 60000 THEN 'High'
        WHEN salary >= 50000 THEN 'Medium'
        ELSE 'Low'
    END AS salary_category
FROM employees;

## Simple CASE

Simple CASE compares a column with specific values.

Example:

SELECT
    name,
    department,
    CASE department
        WHEN 'IT' THEN 'Technology'
        WHEN 'HR' THEN 'Human Resources'
        WHEN 'Finance' THEN 'Accounts'
        ELSE 'Other'
    END AS department_type
FROM employees;

## CASE with WHERE

SELECT name, salary
FROM employees
WHERE
    CASE
        WHEN salary >= 60000 THEN 1
        ELSE 0
    END = 1;

## CASE with ORDER BY

SELECT name, salary
FROM employees
ORDER BY
    CASE
        WHEN salary >= 60000 THEN 1
        ELSE 2
    END;