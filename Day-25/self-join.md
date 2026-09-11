# SQL SELF JOIN

SELF JOIN is a JOIN where a table is joined with itself.

It is useful when records in the same table are related to each other.

## Example

An employee table can contain an employee and their manager.

employees

employee_id | name    | manager_id
101         | Darshan | NULL
102         | Rahul   | 101
103         | Amit    | 101

Here, manager_id refers to another employee_id in the same table.

## Syntax

SELECT
    e.name AS employee,
    m.name AS manager
FROM employees e
LEFT JOIN employees m
ON e.manager_id = m.employee_id;

## Result

employee | manager
Darshan  | NULL
Rahul    | Darshan
Amit     | Darshan

## Important

SELF JOIN uses aliases to treat the same table as two different tables.