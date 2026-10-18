# SQL Employee Interview Queries
# SQL Employee Interview Queries

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

## 5. Find the Third-Highest Distinct Salary

SELECT DISTINCT salary
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET 2;

## 6. Find Employees Earning Above Average Salary

SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

## 7. Find Duplicate Salaries

SELECT salary, COUNT(*) AS total
FROM employees
GROUP BY salary
HAVING COUNT(*) > 1;

## 8. Find Employees Whose Names Start with A

SELECT *
FROM employees
WHERE name LIKE 'A%';

## 9. Find Employees Whose Names End with a

SELECT *
FROM employees
WHERE name LIKE '%a';

## 10. Find Employees Earning Between 40000 and 60000

SELECT *
FROM employees
WHERE salary BETWEEN 40000 AND 60000;

## 11. Find the Total Salary

SELECT SUM(salary) AS total_salary
FROM employees;

## 12. Find the Average Salary

SELECT AVG(salary) AS average_salary
FROM employees;

## 13. Find the Highest-Paid Employee

SELECT *
FROM employees
WHERE salary = (
    SELECT MAX(salary)
    FROM employees
);

## 14. Count Employees in Each Department

SELECT department_id, COUNT(*) AS total_employees
FROM employees
GROUP BY department_id;

## 15. Find Departments with More Than Two Employees

SELECT department_id, COUNT(*) AS total_employees
FROM employees
GROUP BY department_id
HAVING COUNT(*) > 2;