# SQL Aggregate Commands

## Count Employees

SELECT COUNT(*)
FROM employees;

## Total Salary

SELECT SUM(salary)
FROM employees;

## Average Salary

SELECT AVG(salary)
FROM employees;

## Minimum Salary

SELECT MIN(salary)
FROM employees;

## Maximum Salary

SELECT MAX(salary)
FROM employees;

## Count IT Employees

SELECT COUNT(*)
FROM employees
WHERE department = 'IT';

## Total IT Salary

SELECT SUM(salary)
FROM employees
WHERE department = 'IT';