# LIMIT Clause

LIMIT is used to restrict the number of records returned by a query.

## LIMIT Syntax

SELECT column_name
FROM table_name
LIMIT number;

## Limit Records

SELECT *
FROM employees
LIMIT 5;

## Limit Specific Columns

SELECT name, department
FROM employees
LIMIT 3;

## LIMIT with WHERE

SELECT *
FROM employees
WHERE department = 'IT'
LIMIT 2;
