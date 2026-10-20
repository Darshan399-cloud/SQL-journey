# SQL Subqueries

## 1. What Is a Subquery?

A subquery is a query written inside another SQL query.

## 2. Employees Earning Above Average Salary

SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

## 3. Second-Highest Distinct Salary

SELECT MAX(salary) AS second_highest_salary
FROM employees
WHERE salary < (
    SELECT MAX(salary)
    FROM employees
);

## 4. Third-Highest Distinct Salary

SELECT MAX(salary) AS third_highest_salary
FROM employees
WHERE salary < (
    SELECT MAX(salary)
    FROM employees
    WHERE salary < (
        SELECT MAX(salary)
        FROM employees
    )
);

## 5. Employees Earning the Highest Salary

SELECT *
FROM employees
WHERE salary = (
    SELECT MAX(salary)
    FROM employees
);

## 6. Employees Earning More Than Their Department Average

SELECT e.*
FROM employees e
WHERE e.salary > (
    SELECT AVG(e2.salary)
    FROM employees e2
    WHERE e2.department_id = e.department_id
);

## 7. EXISTS

Find departments that have employees.

SELECT d.*
FROM departments d
WHERE EXISTS (
    SELECT 1
    FROM employees e
    WHERE e.department_id = d.department_id
);

## 8. NOT EXISTS

Find departments that have no employees.

SELECT d.*
FROM departments d
WHERE NOT EXISTS (
    SELECT 1
    FROM employees e
    WHERE e.department_id = d.department_id
);

## 9. IN

Find employees who belong to a department listed in the departments table.

SELECT *
FROM employees
WHERE department_id IN (
    SELECT department_id
    FROM departments
);

## 10. Important Note

If fewer distinct salary values exist than the requested rank,
the Nth-highest salary query returns NULL.