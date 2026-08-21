# COUNT, SUM and AVG

## COUNT()

SELECT COUNT(*)
FROM employees;

## COUNT Specific Column

SELECT COUNT(department)
FROM employees;

## SUM()

SELECT SUM(salary)
FROM employees;

## AVG()

SELECT AVG(salary)
FROM employees;

## MIN()

SELECT MIN(salary)
FROM employees;

## MAX()

SELECT MAX(salary)
FROM employees;

## Aggregate Functions with WHERE

SELECT SUM(salary)
FROM employees
WHERE department = 'IT';

## Average Salary of IT Department

SELECT AVG(salary)
FROM employees
WHERE department = 'IT';