# SQL JOINs and Window Functions

## 1. Display Employee and Department Names

SELECT e.name, d.department_name
FROM employees e
INNER JOIN departments d
ON e.department_id = d.department_id;

## 2. Display All Employees, Including Those Without Departments

SELECT e.name, d.department_name
FROM employees e
LEFT JOIN departments d
ON e.department_id = d.department_id;

## 3. Find Departments Without Employees

SELECT d.*
FROM departments d
LEFT JOIN employees e
ON d.department_id = e.department_id
WHERE e.id IS NULL;

## 4. Rank Employees by Salary

SELECT name, salary,
RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;

## 5. Use DENSE_RANK()

SELECT name, salary,
DENSE_RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;

## 6. Assign a Unique Row Number

SELECT name, salary,
ROW_NUMBER() OVER (
    ORDER BY salary DESC, id ASC
) AS row_num
FROM employees;

## 7. Find the Top Two Distinct Salary Ranks in Each Department

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

## 8. Find Departments That Have Employees

SELECT d.*
FROM departments d
WHERE EXISTS (
    SELECT 1
    FROM employees e
    WHERE e.department_id = d.department_id
);

## 9. Find Departments Without Employees

SELECT d.*
FROM departments d
WHERE NOT EXISTS (
    SELECT 1
    FROM employees e
    WHERE e.department_id = d.department_id
);

## 10. Count Employees in Each Department

SELECT d.department_name,
       COUNT(e.id) AS total_employees
FROM departments d
LEFT JOIN employees e
ON d.department_id = e.department_id
GROUP BY d.department_id, d.department_name;