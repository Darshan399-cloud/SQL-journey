# SQL Optimization Commands

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

## Select All Columns

SELECT *
FROM employees;

## Select Required Columns

SELECT
    name,
    salary
FROM employees;

## Use WHERE

SELECT
    name,
    salary
FROM employees
WHERE department = 'IT';

## Use LIMIT

SELECT *
FROM employees
LIMIT 3;

## Create Index

CREATE INDEX idx_employee_department
ON employees(department);

## Display Indexes

SHOW INDEX
FROM employees;

## EXPLAIN Query

EXPLAIN
SELECT *
FROM employees
WHERE department = 'IT';

## EXPLAIN Specific Columns

EXPLAIN
SELECT
    name,
    salary
FROM employees
WHERE department = 'IT';

## Drop Index

DROP INDEX idx_employee_department
ON employees;

## Optimize Table

OPTIMIZE TABLE employees;