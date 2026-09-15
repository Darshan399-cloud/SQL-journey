v
# SQL Subqueries

A subquery is a query written inside another SQL query.

The inner query is executed first and its result is used by the outer query.

## Basic Syntax

SELECT column_name
FROM table_name
WHERE column_name = (
    SELECT column_name
    FROM table_name
    WHERE condition
);

## Example

SELECT name, salary
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

This query finds employees whose salary is greater than the average salary.

## Subquery with MAX

SELECT name, salary
FROM employees
WHERE salary = (
    SELECT MAX(salary)
    FROM employees
);

This query finds the employee with the highest salary.

## Subquery with MIN

SELECT name, salary
FROM employees
WHERE salary = (
    SELECT MIN(salary)
    FROM employees
);

This query finds the employee with the lowest salary.

## Important

A subquery is also called a nested query.

The inner query is written inside parentheses.