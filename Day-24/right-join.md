# SQL RIGHT JOIN

RIGHT JOIN returns all records from the right table and matching records from the left table.

If there is no matching record, NULL is returned for the left table columns.

## Syntax

SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;

## Example

SELECT
    employees.name,
    departments.department_name
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;

## Important

RIGHT JOIN keeps all records from the right table even when there is no match.