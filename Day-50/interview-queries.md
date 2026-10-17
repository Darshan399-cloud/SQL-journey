# Important SQL Interview Queries

## 1. Find All Employees

SELECT * FROM employees;

## 2. Find Employees with Salary Greater Than 50000

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

## 6. Find Employees in Each Department

SELECT department_id, COUNT(*) AS total
FROM employees
GROUP BY department_id;

## 7. Find Duplicate Email Addresses

SELECT email, COUNT(*) AS total
FROM employees
GROUP BY email
HAVING COUNT(*) > 1;

## 8. Find Employees Whose Names Start with A

SELECT *
FROM employees
WHERE name LIKE 'A%';

## 9. Find Employees Without a Department

SELECT *
FROM employees
WHERE department_id IS NULL;

## 10. Sort Employees by Salary

SELECT *
FROM employees
ORDER BY salary DESC;

## 11. Find Employees Earning Above Average Salary

SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

## 12. Find the Top Three Highest-Paid Employees

SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 3;

## 13. Find Department-Wise Average Salary

SELECT department_id, AVG(salary) AS average_salary
FROM employees
GROUP BY department_id;

## 14. Find Employees Who Share the Same Salary

SELECT salary, COUNT(*) AS total
FROM employees
GROUP BY salary
HAVING COUNT(*) > 1;

## 15. Rank Employees by Salary

SELECT name, salary,
DENSE_RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;