# Aggregate Functions

Aggregate functions perform calculations on multiple rows and return a single result.

## COUNT()

COUNT() returns the number of records.

Example:

SELECT COUNT(*)
FROM employees;

## SUM()

SUM() calculates the total value of a numeric column.

Example:

SELECT SUM(salary)
FROM employees;

## AVG()

AVG() calculates the average value of a numeric column.

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