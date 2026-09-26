# SQL Aggregate Functions

Aggregate functions perform calculations on multiple rows and return a single result.

## COUNT()

COUNT() returns the number of rows.

Example:

SELECT COUNT(*)
FROM employees;

## SUM()

SUM() calculates the total value of a numeric column.

Example:

SELECT SUM(salary)
FROM employees;

## AVG()

AVG() calculates the average value.

Example:

SELECT AVG(salary)
FROM employees;

## MIN()

MIN() returns the smallest value.

Example:

SELECT MIN(salary)
FROM employees;

## MAX()

MAX() returns the largest value.

Example:

SELECT MAX(salary)
FROM employees;

## GROUP BY

GROUP BY groups rows with the same values.

Example:

SELECT department, COUNT(*)
FROM employees
GROUP BY department;

## HAVING

HAVING filters grouped results.

Example:

SELECT department, AVG(salary)
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;

## WHERE vs HAVING

WHERE filters rows before grouping.

HAVING filters groups after GROUP BY.