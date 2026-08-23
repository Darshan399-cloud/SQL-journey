# HAVING with Aggregate Functions

## COUNT()

SELECT department, COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) >= 3;

## SUM()

SELECT department, SUM(salary)
FROM employees
GROUP BY department
HAVING SUM(salary) >= 150000;

## AVG()

SELECT department, AVG(salary)
FROM employees
GROUP BY department
HAVING AVG(salary) >= 50000;

## MIN()

SELECT department, MIN(salary)
FROM employees
GROUP BY department
HAVING MIN(salary) > 30000;

## MAX()

SELECT department, MAX(salary)
FROM employees
GROUP BY department
HAVING MAX(salary) > 70000;

## GROUP BY with WHERE and HAVING

SELECT department, AVG(salary)
FROM employees
WHERE salary > 30000
GROUP BY department
HAVING AVG(salary) > 50000;