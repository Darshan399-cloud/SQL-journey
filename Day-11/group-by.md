# GROUP BY Clause

GROUP BY is used to group rows that have the same values in one or more columns.

## GROUP BY Syntax

SELECT column_name, aggregate_function(column_name)
FROM table_name
GROUP BY column_name;

## Group Employees by Department

SELECT department
FROM employees
GROUP BY department;

## Count Employees by Department

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