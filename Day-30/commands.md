# SQL View Commands

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

## Create Basic View

CREATE VIEW employee_details AS
SELECT
    name,
    department,
    salary
FROM employees;

## Display View

SELECT *
FROM employee_details;

## Display Specific Columns

SELECT name, salary
FROM employee_details;

## Create High Salary View

CREATE VIEW high_salary_employees AS
SELECT
    name,
    department,
    salary
FROM employees
WHERE salary >= 60000;

## Display High Salary Employees

SELECT *
FROM high_salary_employees;

## Create or Replace View

CREATE OR REPLACE VIEW employee_details AS
SELECT
    name,
    department
FROM employees;

## Display Updated View

SELECT *
FROM employee_details;

## Drop View

DROP VIEW employee_details;

## Check Remaining View

SELECT *
FROM high_salary_employees;