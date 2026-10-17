# SQL Revision Topics

## 1. SELECT
Used to retrieve data from a table.

SELECT * FROM employees;

## 2. WHERE
Used to filter records.

SELECT * FROM employees
WHERE salary > 30000;

## 3. ORDER BY
Used to sort records.

SELECT * FROM employees
ORDER BY salary DESC;

## 4. LIMIT
Used to restrict the number of returned rows.

SELECT * FROM employees
LIMIT 5;

## 5. Aggregate Functions

COUNT() - Counts rows.
SUM() - Calculates the total.
AVG() - Calculates the average.
MIN() - Finds the minimum value.
MAX() - Finds the maximum value.

## 6. GROUP BY
Groups records with the same value.

SELECT department, COUNT(*)
FROM employees
GROUP BY department;

## 7. HAVING
Filters grouped results.

SELECT department, AVG(salary)
FROM employees
GROUP BY department
HAVING AVG(salary) > 40000;

## 8. JOIN
Combines related data from tables.

SELECT employees.name, departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;

## 9. Subquery
A query written inside another query.

SELECT name
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

## 10. CASE
Returns a result based on conditions.

SELECT name, salary,
CASE
    WHEN salary >= 50000 THEN 'High Salary'
    ELSE 'Regular Salary'
END AS salary_status
FROM employees;

## 11. Constraints
PRIMARY KEY - Uniquely identifies each row.
FOREIGN KEY - Connects related tables.
UNIQUE - Prevents duplicate values.
NOT NULL - Prevents NULL values.
CHECK - Checks a condition.
DEFAULT - Sets a default value.

## 12. CTE
A Common Table Expression uses the WITH clause.

WITH high_salary AS (
    SELECT *
    FROM employees
    WHERE salary > 50000
)
SELECT * FROM high_salary;

## 13. Window Function
Calculates results across related rows without combining them into one row.

SELECT name, salary,
ROW_NUMBER() OVER (ORDER BY salary DESC) AS row_num
FROM employees;