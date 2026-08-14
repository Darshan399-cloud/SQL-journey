# WHERE Clause

WHERE is used to filter records based on a condition.

## WHERE Syntax

SELECT column_name
FROM table_name
WHERE condition;

## Filter by ID

SELECT *
FROM employees
WHERE id = 1;

## Filter by Name

SELECT *
FROM employees
WHERE name = 'Rahul';

## Filter by Salary

SELECT *
FROM employees
WHERE salary > 50000;

## Filter by Department

SELECT *
FROM employees
WHERE department = 'IT';