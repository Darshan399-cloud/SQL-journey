# SQL CASE Statement Commands

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    salary DECIMAL(10,2)
);

## Insert Records

INSERT INTO employees
VALUES (101, 'Darshan', 'IT', 50000);

INSERT INTO employees
VALUES (102, 'Rahul', 'IT', 65000);

INSERT INTO employees
VALUES (103, 'Amit', 'HR', 45000);

INSERT INTO employees
VALUES (104, 'Priya', 'Finance', 70000);

INSERT INTO employees
VALUES (105, 'Sneha', 'HR', 55000);

## Salary Category

SELECT
    name,
    salary,
    CASE
        WHEN salary >= 60000 THEN 'High'
        WHEN salary >= 50000 THEN 'Medium'
        ELSE 'Low'
    END AS salary_category
FROM employees;

## Department Category

SELECT
    name,
    department,
    CASE department
        WHEN 'IT' THEN 'Technology'
        WHEN 'HR' THEN 'Human Resources'
        WHEN 'Finance' THEN 'Accounts'
        ELSE 'Other'
    END AS department_type
FROM employees;

## Count High Salary Employees

SELECT
    COUNT(
        CASE
            WHEN salary >= 60000 THEN 1
        END
    ) AS high_salary_employees
FROM employees;

## Calculate High Salary Total

SELECT
    SUM(
        CASE
            WHEN salary >= 60000 THEN salary
            ELSE 0
        END
    ) AS high_salary_total
FROM employees;

## Employee Salary Status

SELECT
    name,
    salary,
    CASE
        WHEN salary >= 70000 THEN 'Excellent'
        WHEN salary >= 60000 THEN 'Good'
        WHEN salary >= 50000 THEN 'Average'
        ELSE 'Needs Improvement'
    END AS salary_status
FROM employees;