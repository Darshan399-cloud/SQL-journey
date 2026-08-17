# ORDER BY Clause

ORDER BY is used to sort records based on one or more columns.

## ORDER BY Syntax

SELECT column_name
FROM table_name
ORDER BY column_name;

## Ascending Order

SELECT *
FROM employees
ORDER BY salary ASC;

## Descending Order

SELECT *
FROM employees
ORDER BY salary DESC;

## Sort by Name

SELECT *
FROM employees
ORDER BY name ASC;

## Sort by Multiple Columns

SELECT *
FROM employees
ORDER BY department ASC, salary DESC;