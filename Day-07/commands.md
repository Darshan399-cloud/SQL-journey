# SQL LIMIT Commands

## Limit Records

SELECT *
FROM employees
LIMIT 5;

## Limit Specific Columns

SELECT name, salary
FROM employees
LIMIT 3;

## Highest Salaries

SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 3;

## Lowest Salaries

SELECT *
FROM employees
ORDER BY salary ASC
LIMIT 3;

## LIMIT with WHERE

SELECT *
FROM employees
WHERE department = 'IT'
LIMIT 2;

## LIMIT with WHERE and ORDER BY

SELECT *
FROM employees
WHERE department = 'IT'
ORDER BY salary DESC
LIMIT 3;
