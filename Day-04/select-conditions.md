# SELECT Options

## Select All Columns

SELECT *
FROM employees;

## Select Specific Columns

SELECT name, salary
FROM employees;

## Select Unique Values

SELECT DISTINCT department
FROM employees;

## Select Column with Alias

SELECT name AS employee_name
FROM employees;

## Multiple Column Aliases

SELECT
    name AS employee_name,
    department AS dept
FROM employees;