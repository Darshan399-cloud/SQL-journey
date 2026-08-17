# SQL ORDER BY Commands

## Sort Salary in Ascending Order

SELECT *
FROM employees
ORDER BY salary ASC;

## Sort Salary in Descending Order

SELECT *
FROM employees
ORDER BY salary DESC;

## Sort Name Alphabetically

SELECT *
FROM employees
ORDER BY name ASC;

## Sort Name in Reverse Alphabetical Order

SELECT *
FROM employees
ORDER BY name DESC;

## Sort by Multiple Columns

SELECT *
FROM employees
ORDER BY department ASC, salary DESC;