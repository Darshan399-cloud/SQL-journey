# SQL UNION

UNION is used to combine the result of two or more SELECT statements.

UNION removes duplicate records from the final result.

## Syntax

SELECT column1
FROM table1

UNION

SELECT column1
FROM table2;

## Example

SELECT name
FROM employees

UNION

SELECT name
FROM managers;

## Important Rules

1. Each SELECT must have the same number of columns.
2. Corresponding columns should have compatible data types.
3. UNION removes duplicate rows.
4. The column names come from the first SELECT statement.