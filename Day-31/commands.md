# SQL Index Commands

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(150),
    department VARCHAR(100),
    salary DECIMAL(10,2)
);

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 'darshan@example.com', 'IT', 50000);

INSERT INTO employees
VALUES (102, 'Rahul', 'rahul@example.com', 'IT', 65000);

INSERT INTO employees
VALUES (103, 'Amit', 'amit@example.com', 'HR', 45000);

INSERT INTO employees
VALUES (104, 'Priya', 'priya@example.com', 'Finance', 70000);

INSERT INTO employees
VALUES (105, 'Sneha', 'sneha@example.com', 'HR', 55000);

## Create Index on Name

CREATE INDEX idx_employee_name
ON employees (name);

## Create Index on Department

CREATE INDEX idx_employee_department
ON employees (department);

## Create Unique Index on Email

CREATE UNIQUE INDEX idx_employee_email
ON employees (email);

## Create Composite Index

CREATE INDEX idx_department_salary
ON employees (department, salary);

## Display Indexes

SHOW INDEX FROM employees;

## Query Using Indexed Column

SELECT *
FROM employees
WHERE name = 'Darshan';

## Query Using Department

SELECT *
FROM employees
WHERE department = 'IT';

## Drop Name Index

DROP INDEX idx_employee_name
ON employees;

## Drop Department Index

DROP INDEX idx_employee_department
ON employees;

## Drop Composite Index

DROP INDEX idx_department_salary
ON employees;