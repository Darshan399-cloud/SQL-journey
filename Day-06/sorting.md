# Sorting Data

## ASC

ASC stands for Ascending.

Numbers are sorted from smallest to largest.

Text is sorted alphabetically.

Example:

SELECT *
FROM employees
ORDER BY salary ASC;

## DESC

DESC stands for Descending.

Numbers are sorted from largest to smallest.

Text is sorted in reverse alphabetical order.

Example:

SELECT *
FROM employees
ORDER BY salary DESC;

## Multiple Column Sorting

Records can be sorted using multiple columns.

Example:

SELECT *
FROM employees
ORDER BY department ASC, salary DESC;