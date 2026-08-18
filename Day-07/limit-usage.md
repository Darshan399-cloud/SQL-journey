# LIMIT Usage

## LIMIT with ORDER BY

LIMIT can be used with ORDER BY to retrieve a specific number of sorted records.

Example:

SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 3;

## Highest Salaries

SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 5;

## Lowest Salaries

SELECT *
FROM employees
ORDER BY salary ASC
LIMIT 5;

## LIMIT with WHERE and ORDER BY

SELECT *
FROM employees
WHERE department = 'IT'
ORDER BY salary DESC
LIMIT 3;
