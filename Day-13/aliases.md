# SQL Aliases

An alias is a temporary name given to a column or table.

Aliases are commonly used to make query results easier to understand.

## Column Alias

SELECT name AS employee_name
FROM employees;

## Table Alias

SELECT e.name
FROM employees AS e;

## Alias without AS

SELECT name employee_name
FROM employees;

## Alias with Expression

SELECT salary * 12 AS annual_salary
FROM employees;

## Alias with Aggregate Function

SELECT AVG(salary) AS average_salary
FROM employees;