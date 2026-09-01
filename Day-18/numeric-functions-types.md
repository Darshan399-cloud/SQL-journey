# Numeric Function Examples

## ROUND()

SELECT salary, ROUND(salary / 12, 2) AS monthly_salary
FROM employees;

## CEIL()

SELECT CEIL(125.45) AS rounded_value;

## FLOOR()

SELECT FLOOR(125.45) AS rounded_value;

## ABS()

SELECT ABS(-500) AS absolute_value;

## MOD()

SELECT MOD(100, 30) AS remainder;

## POWER()

SELECT POWER(5, 2) AS result;

## Numeric Functions with Columns

SELECT salary, ROUND(salary * 1.10, 2) AS increased_salary
FROM employees;