# SQL GROUP BY

GROUP BY is used to group rows that have the same values.

## Basic Syntax

SELECT column_name, aggregate_function(column_name)
FROM table_name
GROUP BY column_name;

## Group by Department

SELECT
    department,
    COUNT(*) AS employee_count
FROM employees
GROUP BY department;

## Average Salary by Department

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department;

## Total Salary by Department

SELECT
    department,
    SUM(salary) AS total_salary
FROM employees
GROUP BY department;

## Maximum Salary by Department

SELECT
    department,
    MAX(salary) AS maximum_salary
FROM employees
GROUP BY department;

## Minimum Salary by Department

SELECT
    department,
    MIN(salary) AS minimum_salary
FROM employees
GROUP BY department;

## GROUP BY with HAVING

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;