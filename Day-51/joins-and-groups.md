# SQL JOIN and Grouping Interview Queries

## 1. INNER JOIN

Display employees with their department names.

SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d
ON e.department_id = d.department_id;

## 2. LEFT JOIN

Display all employees, including those without a department.

SELECT e.name, d.department_name
FROM employees e
LEFT JOIN departments d
ON e.department_id = d.department_id;

## 3. Find Employees Without a Department

SELECT *
FROM employees
WHERE department_id IS NULL;

## 4. Find Departments Without Employees

SELECT d.department_id, d.department_name
FROM departments d
LEFT JOIN employees e
ON d.department_id = e.department_id
WHERE e.id IS NULL;

## 5. Department-Wise Average Salary

SELECT department_id, AVG(salary) AS average_salary
FROM employees
GROUP BY department_id;

## 6. Department-Wise Maximum Salary

SELECT department_id, MAX(salary) AS highest_salary
FROM employees
GROUP BY department_id;

## 7. Department-Wise Minimum Salary

SELECT department_id, MIN(salary) AS lowest_salary
FROM employees
GROUP BY department_id;

## 8. Department-Wise Total Salary

SELECT department_id, SUM(salary) AS total_salary
FROM employees
GROUP BY department_id;

## 9. Highest Salary in Each Department

SELECT department_id, MAX(salary) AS highest_salary
FROM employees
GROUP BY department_id;

## 10. Rank Employees by Salary

SELECT name, salary,
DENSE_RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;

## 11. Top Two Salaries in Each Department

SELECT name, salary, department_id
FROM (
    SELECT name, salary, department_id,
           DENSE_RANK() OVER (
               PARTITION BY department_id
               ORDER BY salary DESC
           ) AS salary_rank
    FROM employees
) AS ranked
WHERE salary_rank <= 2;