# SQL Common Table Expressions (CTE)

A CTE is a temporary named result set that can be used inside a SQL query.

CTE is created using the WITH keyword.

## Basic Syntax

WITH cte_name AS (
    SELECT column1, column2
    FROM table_name
)
SELECT *
FROM cte_name;

## Simple CTE

WITH employee_data AS (
    SELECT
        name,
        salary
    FROM employees
)
SELECT *
FROM employee_data;

## CTE with WHERE

WITH high_salary AS (
    SELECT
        name,
        salary
    FROM employees
    WHERE salary >= 60000
)
SELECT *
FROM high_salary;

## CTE with Aggregate Function

WITH department_salary AS (
    SELECT
        department,
        AVG(salary) AS average_salary
    FROM employees
    GROUP BY department
)
SELECT *
FROM department_salary;

## CTE with Condition

WITH department_salary AS (
    SELECT
        department,
        AVG(salary) AS average_salary
    FROM employees
    GROUP BY department
)
SELECT *
FROM department_salary
WHERE average_salary > 50000;

## Multiple CTEs

WITH employee_count AS (
    SELECT
        department,
        COUNT(*) AS total_employees
    FROM employees
    GROUP BY department
),
salary_data AS (
    SELECT
        department,
        AVG(salary) AS average_salary
    FROM employees
    GROUP BY department
)
SELECT
    employee_count.department,
    employee_count.total_employees,
    salary_data.average_salary
FROM employee_count
JOIN salary_data
ON employee_count.department = salary_data.department;

## Advantages

- Makes complex queries easier to read
- Improves query organization
- Can break a large query into smaller parts
- Useful for recursive queries