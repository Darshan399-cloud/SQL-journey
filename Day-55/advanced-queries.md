# Advanced SQL Interview Queries

## 1. Find the Second-Highest Distinct Salary

SELECT MAX(salary) AS second_highest_salary
FROM employees
WHERE salary < (
    SELECT MAX(salary)
    FROM employees
);

## 2. Find the Third-Highest Distinct Salary

SELECT DISTINCT salary
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET 2;

## 3. Find Employees Earning Above Average Salary

SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

## 4. Find Employees Earning More Than Their Department Average

SELECT e.*
FROM employees e
WHERE e.department_id IS NOT NULL
AND e.salary > (
    SELECT AVG(e2.salary)
    FROM employees e2
    WHERE e2.department_id = e.department_id
);

## 5. Find Duplicate Salaries

SELECT salary, COUNT(*) AS total
FROM employees
GROUP BY salary
HAVING COUNT(*) > 1;

## 6. Find Salaries That Occur Only Once

SELECT salary
FROM employees
GROUP BY salary
HAVING COUNT(*) = 1;

## 7. Find the Highest Salary in Each Department

SELECT department_id, MAX(salary) AS highest_salary
FROM employees
WHERE department_id IS NOT NULL
GROUP BY department_id;

## 8. Find Employees with the Highest Salary in Each Department

SELECT e.*
FROM employees e
WHERE e.department_id IS NOT NULL
AND e.salary = (
    SELECT MAX(e2.salary)
    FROM employees e2
    WHERE e2.department_id = e.department_id
);

## 9. Use a CTE to Find High-Salary Employees

WITH high_salary AS (
    SELECT *
    FROM employees
    WHERE salary > 50000
)
SELECT *
FROM high_salary;

## 10. Categorize Employees by Salary

SELECT name, salary,
CASE
    WHEN salary >= 60000 THEN 'High'
    WHEN salary >= 40000 THEN 'Medium'
    ELSE 'Low'
END AS salary_category
FROM employees;