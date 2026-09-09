# SQL JOINs

SQL JOIN is used to combine rows from two or more tables based on a related column.

## Why JOIN is Used

JOIN allows us to retrieve related data stored in different tables.

Example:

departments

department_id | department_name
1             | IT
2             | HR

employees

employee_id | name    | department_id
101         | Darshan | 1
102         | Rahul   | 2

The department_id connects both tables.

## Basic Syntax

SELECT columns
FROM table1
JOIN table2
ON table1.column = table2.column;