# SQL IN and BETWEEN Commands

## IN with Departments

SELECT *
FROM employees
WHERE department IN ('IT', 'HR');

## IN with IDs

SELECT *
FROM employees
WHERE id IN (1, 2, 5);

## NOT IN

SELECT *
FROM employees
WHERE department NOT IN ('HR', 'Finance');

## BETWEEN Salary

SELECT *
FROM employees
WHERE salary BETWEEN 40000 AND 60000;

## BETWEEN ID

SELECT *
FROM employees
WHERE id BETWEEN 1 AND 5;

## NOT BETWEEN

SELECT *
FROM employees
WHERE salary NOT BETWEEN 40000 AND 60000;

## IN with BETWEEN

SELECT *
FROM employees
WHERE department IN ('IT', 'HR')
AND salary BETWEEN 40000 AND 60000;