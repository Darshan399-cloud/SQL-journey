# BETWEEN Operator

BETWEEN is used to select values within a specified range.

## BETWEEN Syntax

SELECT column_name
FROM table_name
WHERE column_name BETWEEN value1 AND value2;

## BETWEEN with Salary

SELECT *
FROM employees
WHERE salary BETWEEN 40000 AND 60000;

## BETWEEN with ID

SELECT *
FROM employees
WHERE id BETWEEN 1 AND 5;

## NOT BETWEEN

SELECT *
FROM employees
WHERE salary NOT BETWEEN 40000 AND 60000;

## BETWEEN with IN

SELECT *
FROM employees
WHERE department IN ('IT', 'HR')
AND salary BETWEEN 40000 AND 60000;