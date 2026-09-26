# SQL Aggregate Function Commands

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    salary DECIMAL(10,2)
);

## Insert Employees

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

## COUNT

SELECT COUNT(*)
FROM employees;

## SUM

SELECT SUM(salary)
FROM employees;

## AVG

SELECT AVG(salary)
FROM employees;

## MIN

SELECT MIN(salary)
FROM employees;

## MAX

SELECT MAX(salary)
FROM employees;

## COUNT by Department

SELECT
    department,
    COUNT(*) AS employee_count
FROM employees
GROUP BY department;

## SUM by Department

SELECT
    department,
    SUM(salary) AS total_salary
FROM employees
GROUP BY department;

## AVG by Department

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department;

## HAVING

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;

## WHERE with GROUP BY

SELECT
    department,
    AVG(salary) AS average_salary
FROM employees
WHERE salary >= 50000
GROUP BY department;