# LIKE Operator

LIKE is used to search for a specific pattern in a column.

## LIKE Syntax

SELECT column_name
FROM table_name
WHERE column_name LIKE pattern;

## Starts With

SELECT *
FROM employees
WHERE name LIKE 'A%';

## Ends With

SELECT *
FROM employees
WHERE name LIKE '%a';

## Contains

SELECT *
FROM employees
WHERE name LIKE '%it%';

## NOT LIKE

SELECT *
FROM employees
WHERE name NOT LIKE 'A%';