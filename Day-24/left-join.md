# SQL LEFT JOIN

LEFT JOIN returns all records from the left table and matching records from the right table.

If there is no matching record, NULL is returned for the right table columns.

## Syntax

SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;

## Example

SELECT
    employees.name,
    departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id;

## Important

LEFT JOIN keeps all records from the left table even when there is no match.