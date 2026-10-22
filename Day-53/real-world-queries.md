# SQL Real-World Queries

## 1. Find Employees Earning More Than 50000

SELECT *
FROM employees
WHERE salary > 50000;

## 2. Find the Highest-Paid Employee

SELECT *
FROM employees
WHERE salary = (
    SELECT MAX(salary)
    FROM employees
);

## 3. Find the Second-Highest Distinct Salary

SELECT MAX(salary) AS second_highest_salary
FROM employees
WHERE salary < (
    SELECT MAX(salary)
    FROM employees
);

## 4. Find Employees Earning Above Average Salary

SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

## 5. Count Employees in Each Department

SELECT department_id, COUNT(*) AS total_employees
FROM employees
GROUP BY department_id;

## 6. Find Departments with More Than Two Employees

SELECT department_id, COUNT(*) AS total_employees
FROM employees
WHERE department_id IS NOT NULL
GROUP BY department_id
HAVING COUNT(*) > 2;

## 7. Find Duplicate Salaries

SELECT salary, COUNT(*) AS total
FROM employees
GROUP BY salary
HAVING COUNT(*) > 1;

## 8. Categorize Employees by Salary

SELECT name, salary,
CASE
    WHEN salary >= 60000 THEN 'High'
    WHEN salary >= 40000 THEN 'Medium'
    ELSE 'Low'
END AS salary_category
FROM employees;

## 9. Find Employees Without a Department

SELECT *
FROM employees
WHERE department_id IS NULL;

## 10. Display the Top Three Highest Salary Values

SELECT DISTINCT salary
FROM employees
ORDER BY salary DESC
LIMIT 3;

## 11. Find Employees with Names Starting with A

SELECT *
FROM employees
WHERE name LIKE 'A%';

## 12. Calculate Total Salary by Department

SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id;