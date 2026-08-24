# Column and Table Aliases

## Column Alias

SELECT name AS employee_name
FROM employees;

## Multiple Column Aliases

SELECT
    name AS employee_name,
    department AS department_name,
    salary AS employee_salary
FROM employees;

## Table Alias

SELECT e.name, e.salary
FROM employees AS e;

## Multiple Table Aliases

SELECT e.name, d.department_name
FROM employees AS e
JOIN departments AS d
ON e.department_id = d.id;

## Aggregate Alias

SELECT
    department,
    COUNT(*) AS employee_count,
    SUM(salary) AS total_salary
FROM employees
GROUP BY department;