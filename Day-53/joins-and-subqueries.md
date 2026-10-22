# SQL JOINs and Subqueries

## 1. Display Employee and Department Names

SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d
ON e.department_id = d.department_id;

## 2. Display All Employees and Their Departments

SELECT e.name, d.department_name
FROM employees e
LEFT JOIN departments d
ON e.department_id = d.department_id;

## 3. Find Departments Without Employees

SELECT d.department_id, d.department_name
FROM departments d
LEFT JOIN employees e
ON d.department_id = e.department_id
WHERE e.id IS NULL;

## 4. Find Employees Earning More Than Their Department Average

SELECT e.*
FROM employees e
WHERE e.department_id IS NOT NULL
AND e.salary > (
    SELECT AVG(e2.salary)
    FROM employees e2
    WHERE e2.department_id = e.department_id
);

## 5. Rank Employees by Salary

SELECT name, salary,
DENSE_RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;

## 6. Find the Highest Salary in Each Department

SELECT department_id, MAX(salary) AS highest_salary
FROM employees
WHERE department_id IS NOT NULL
GROUP BY department_id;

## 7. Find Employees Who Earn the Highest Salary in Their Department

SELECT e.*
FROM employees e
WHERE e.department_id IS NOT NULL
AND e.salary = (
    SELECT MAX(e2.salary)
    FROM employees e2
    WHERE e2.department_id = e.department_id
);

## 8. Use a CTE to Find High-Salary Employees

WITH high_salary AS (
    SELECT *
    FROM employees
    WHERE salary > 50000
)
SELECT *
FROM high_salary;

## 9. Find Departments That Have Employees

SELECT d.*
FROM departments d
WHERE EXISTS (
    SELECT 1
    FROM employees e
    WHERE e.department_id = d.department_id
);

## 10. Find Departments That Have No Employees

SELECT d.*
FROM departments d
WHERE NOT EXISTS (
    SELECT 1
    FROM employees e
    WHERE e.department_id = d.department_id
);