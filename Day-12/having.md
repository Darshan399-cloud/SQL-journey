# HAVING Clause

HAVING is used to filter grouped records.

HAVING is commonly used with GROUP BY and aggregate functions.

## HAVING Syntax

SELECT column_name, aggregate_function(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;

## HAVING with COUNT()

SELECT department, COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 2;

## HAVING with SUM()

SELECT department, SUM(salary)
FROM employees
GROUP BY department
HAVING SUM(salary) > 100000;

## HAVING with AVG()

SELECT department, AVG(salary)
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;