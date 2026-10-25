# SQL Mock Interview - Practical Queries

## 1. Display All Employees

SELECT * FROM employees;

## 2. Find Employees Earning More Than 50000

SELECT *
FROM employees
WHERE salary > 50000;

## 3. Find the Highest Salary

SELECT MAX(salary) AS highest_salary
FROM employees;

## 4. Find the Second-Highest Distinct Salary

SELECT MAX(salary) AS second_highest_salary
FROM employees
WHERE salary < (
    SELECT MAX(salary)
    FROM employees
);

## 5. Count Employees

SELECT COUNT(*) AS total_employees
FROM employees;

## 6. Find Average Salary

SELECT AVG(salary) AS average_salary
FROM employees;

## 7. Find Duplicate Salaries

SELECT salary, COUNT(*) AS total
FROM employees
GROUP BY salary
HAVING COUNT(*) > 1;

## 8. Find Employees Whose Names Start with A

SELECT *
FROM employees
WHERE name LIKE 'A%';

## 9. Display Employee and Department Names

SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d
ON e.department_id = d.department_id;

## 10. Display All Employees, Including Those Without Departments

SELECT e.name, d.department_name
FROM employees e
LEFT JOIN departments d
ON e.department_id = d.department_id;

## 11. Find Employees Earning Above Average Salary

SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

## 12. Find Department-Wise Employee Count

SELECT department_id, COUNT(*) AS total
FROM employees
GROUP BY department_id;

## 13. Find Departments with Average Salary Above 50000

SELECT department_id, AVG(salary) AS average_salary
FROM employees
WHERE department_id IS NOT NULL
GROUP BY department_id
HAVING AVG(salary) > 50000;

## 14. Rank Employees by Salary

SELECT name, salary,
DENSE_RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;

## 15. Categorize Salaries Using CASE

SELECT name, salary,
CASE
    WHEN salary >= 60000 THEN 'High'
    WHEN salary >= 40000 THEN 'Medium'
    ELSE 'Low'
END AS salary_category
FROM employees;