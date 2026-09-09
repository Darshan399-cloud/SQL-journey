# SQL INNER JOIN

INNER JOIN returns only the records that have matching values in both tables.

## Syntax

SELECT columns
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;

## Example

SELECT
    employees.name,
    departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;

## Result

name    | department_name
Darshan | IT
Rahul   | HR

Only matching records are returned.