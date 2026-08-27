# IN Operator

IN is used to specify multiple values in a WHERE clause.

## IN Syntax

SELECT column_name
FROM table_name
WHERE column_name IN (value1, value2);

## IN with Strings

SELECT *
FROM employees
WHERE department IN ('IT', 'HR');

## IN with Numbers

SELECT *
FROM employees
WHERE id IN (1, 3, 5);

## NOT IN

SELECT *
FROM employees
WHERE department NOT IN ('HR', 'Finance');