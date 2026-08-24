# SQL Alias Commands

## Column Alias

SELECT name AS employee_name
FROM employees;

## Multiple Column Aliases

SELECT
    name AS employee_name,
    salary AS employee_salary
FROM employees;

## Table Alias

SELECT e.name
FROM employees AS e;

## Expression Alias

SELECT salary * 12 AS annual_salary
FROM employees;

## Aggregate Alias

SELECT COUNT(*) AS employee_count
FROM employees;

## Department-wise Alias

SELECT
    department AS department_name,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department;