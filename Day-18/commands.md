# SQL Numeric Function Commands

## ROUND

SELECT ROUND(125.678, 2);

## CEIL

SELECT CEIL(125.678);

## FLOOR

SELECT FLOOR(125.678);

## ABS

SELECT ABS(-100);

## MOD

SELECT MOD(10, 3);

## POWER

SELECT POWER(2, 3);

## Round Salary

SELECT ROUND(salary, 2)
FROM employees;

## Calculate Increased Salary

SELECT salary, ROUND(salary * 1.10, 2) AS increased_salary
FROM employees;