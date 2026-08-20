# DELETE Statement

DELETE is used to remove existing records from a table.

## DELETE Syntax

DELETE FROM table_name
WHERE condition;

## Delete Specific Record

DELETE FROM employees
WHERE id = 1;

## Delete by Name

DELETE FROM employees
WHERE name = 'Rahul';

## Delete by Department

DELETE FROM employees
WHERE department = 'HR';