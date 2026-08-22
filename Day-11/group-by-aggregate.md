# GROUP BY with Aggregate Functions

## COUNT()

SELECT department, COUNT(*)
FROM employees
GROUP BY department;

## SUM()

SELECT department, SUM(salary)
FROM employees
GROUP BY department;

## AVG()

SELECT department, AVG(salary)
FROM employees
GROUP BY department;

## MIN()

SELECT department, MIN(salary)
FROM employees
GROUP BY department;

## MAX()

SELECT department, MAX(salary)
FROM employees
GROUP BY department;

## Multiple Aggregate Functions

SELECT
    department,
    COUNT(*) AS employee_count,
    SUM(salary) AS total_salary,
    AVG(salary) AS average_salary,
    MIN(salary) AS minimum_salary,
    MAX(salary) AS maximum_salary
FROM employees
GROUP BY department;