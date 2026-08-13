# SELECT Statement

SELECT is used to retrieve data from a table.

## SELECT Syntax

SELECT column_name
FROM table_name;

## Select All Columns

SELECT *
FROM employees;

## Select Specific Columns

SELECT name, department
FROM employees;

## Select Multiple Columns

SELECT id, name, department, salary
FROM employees;

## SELECT DISTINCT

SELECT DISTINCT department
FROM employees;

## Column Alias

SELECT name AS employee_name
FROM employees;