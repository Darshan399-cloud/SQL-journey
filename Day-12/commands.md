# SQL HAVING Commands

## Filter by Employee Count

SELECT department, COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 2;

## Filter by Total Salary

SELECT department, SUM(salary)
FROM employees
GROUP BY department
HAVING SUM(salary) > 100000;

## Filter by Average Salary

SELECT department, AVG(salary)
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;

## Filter by Minimum Salary

SELECT department, MIN(salary)
FROM employees
GROUP BY department
HAVING MIN(salary) > 30000;

## Filter by Maximum Salary

SELECT department, MAX(salary)
FROM employees
GROUP BY department
HAVING MAX(salary) > 70000;