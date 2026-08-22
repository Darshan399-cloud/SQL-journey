# SQL GROUP BY Commands

## Group by Department

SELECT department
FROM employees
GROUP BY department;

## Count by Department

SELECT department, COUNT(*)
FROM employees
GROUP BY department;

## Total Salary by Department

SELECT department, SUM(salary)
FROM employees
GROUP BY department;

## Average Salary by Department

SELECT department, AVG(salary)
FROM employees
GROUP BY department;

## Minimum Salary by Department

SELECT department, MIN(salary)
FROM employees
GROUP BY department;

## Maximum Salary by Department

SELECT department, MAX(salary)
FROM employees
GROUP BY department;