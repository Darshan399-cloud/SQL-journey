# SQL CTE Commands

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    salary DECIMAL(10,2)
);

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 'IT', 50000);

INSERT INTO employees
VALUES (102, 'Rahul', 'IT', 65000);

INSERT INTO employees
VALUES (103, 'Amit', 'HR', 45000);

INSERT INTO employees
VALUES (104, 'Priya', 'Finance', 70000);

INSERT INTO employees
VALUES (105, 'Sneha', 'HR', 55000);

## Simple CTE

WITH employee_data AS (
    SELECT
        name,
        department,
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

## CTE with GROUP BY

WITH department_data AS (
    SELECT
        department,
        COUNT(*) AS total_employees,
        AVG(salary) AS average_salary
    FROM employees
    GROUP BY department
)
SELECT *
FROM department_data;

## CTE with HAVING

WITH department_data AS (
    SELECT
        department,
        AVG(salary) AS average_salary
    FROM employees
    GROUP BY department
)
SELECT *
FROM department_data
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

## Recursive CTE

WITH RECURSIVE numbers AS (

    SELECT 1 AS number

    UNION ALL

    SELECT number + 1
    FROM numbers
    WHERE number < 10
)
SELECT *
FROM numbers;