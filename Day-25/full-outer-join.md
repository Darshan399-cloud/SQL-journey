# SQL FULL OUTER JOIN

FULL OUTER JOIN returns all records from both tables.

It returns matching records and also unmatched records from both tables.

## Syntax

SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;

## Important

MySQL does not directly support FULL OUTER JOIN.

In MySQL, FULL OUTER JOIN can be simulated using LEFT JOIN, RIGHT JOIN and UNION.

## MySQL Example

SELECT
    employees.name,
    departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id

UNION

SELECT
    employees.name,
    departments.department_name
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;