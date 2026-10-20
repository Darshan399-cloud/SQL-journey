# Advanced SQL Interview Queries

## 1. CTE - Common Table Expression

WITH high_salary AS (
    SELECT *
    FROM employees
    WHERE salary > 50000
)
SELECT *
FROM high_salary;

## 2. ROW_NUMBER()

Assign a unique row number to each employee.

SELECT name, salary,
ROW_NUMBER() OVER (ORDER BY salary DESC) AS row_num
FROM employees;

## 3. RANK()

Employees with the same salary receive the same rank.
The next rank may be skipped.

SELECT name, salary,
RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;

## 4. DENSE_RANK()

Employees with the same salary receive the same rank.
The next rank is not skipped.

SELECT name, salary,
DENSE_RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;

## 5. Top Two Salary Ranks in Each Department

SELECT name, salary, department_id
FROM (
    SELECT name, salary, department_id,
           DENSE_RANK() OVER (
               PARTITION BY department_id
               ORDER BY salary DESC
           ) AS salary_rank
    FROM employees
    WHERE department_id IS NOT NULL
) AS ranked
WHERE salary_rank <= 2;

## 6. CASE Statement

SELECT name, salary,
CASE
    WHEN salary >= 60000 THEN 'High'
    WHEN salary >= 40000 THEN 'Medium'
    ELSE 'Low'
END AS salary_category
FROM employees;

## 7. Find Duplicate Salaries

SELECT salary, COUNT(*) AS total
FROM employees
GROUP BY salary
HAVING COUNT(*) > 1;

## 8. Find Employees with Unique Salaries

SELECT salary
FROM employees
GROUP BY salary
HAVING COUNT(*) = 1;

## 9. Department-Wise Average Salary

SELECT department_id, AVG(salary) AS average_salary
FROM employees
GROUP BY department_id;

## 10. Employees Earning More Than 50000

SELECT name, salary
FROM employees
WHERE salary > 50000
ORDER BY salary DESC;