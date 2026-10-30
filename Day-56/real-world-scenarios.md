# SQL Real-World Scenarios

## 1. Find Employees Earning More Than 50000

SELECT *
FROM employees
WHERE salary > 50000;

## 2. Find Employees Who Joined After a Specific Date

SELECT *
FROM employees
WHERE joining_date > '2025-01-01';

## 3. Find Employees Without a Department

SELECT *
FROM employees
WHERE department_id IS NULL;

## 4. Find Employees with Their Department Names

SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d
ON e.department_id = d.department_id;

## 5. Find Department-Wise Employee Count

SELECT department_id, COUNT(*) AS total_employees
FROM employees
WHERE department_id IS NOT NULL
GROUP BY department_id;

## 6. Find Employees Earning Above Company Average

SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

## 7. Find Highest-Paid Employee in Each Department

SELECT e.*
FROM employees e
WHERE e.department_id IS NOT NULL
AND e.salary = (
    SELECT MAX(e2.salary)
    FROM employees e2
    WHERE e2.department_id = e.department_id
);

## 8. Find Employees Who Joined in 2025

SELECT *
FROM employees
WHERE YEAR(joining_date) = 2025;

## 9. Calculate Total Salary by Department

SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id;

## 10. Find Employees with Duplicate Salaries

SELECT salary, COUNT(*) AS total
FROM employees
GROUP BY salary
HAVING COUNT(*) > 1;