# SQL IN, EXISTS and NOT EXISTS Commands

## Create Departments Table

CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(100),
    location VARCHAR(100)
);

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department_id INT,
    salary DECIMAL(10,2)
);

## Insert Departments

INSERT INTO departments
VALUES (1, 'IT', 'Pune');

INSERT INTO departments
VALUES (2, 'HR', 'Mumbai');

INSERT INTO departments
VALUES (3, 'Finance', 'Pune');

INSERT INTO departments
VALUES (4, 'Marketing', 'Nashik');

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 1, 50000);

INSERT INTO employees
VALUES (102, 'Rahul', 2, 60000);

INSERT INTO employees
VALUES (103, 'Amit', 3, 55000);

INSERT INTO employees
VALUES (104, 'Priya', 4, 65000);

## IN with Subquery

SELECT name, department_id
FROM employees
WHERE department_id IN (
    SELECT department_id
    FROM departments
    WHERE location = 'Pune'
);

## NOT IN with Subquery

SELECT name, department_id
FROM employees
WHERE department_id NOT IN (
    SELECT department_id
    FROM departments
    WHERE location = 'Pune'
);

## EXISTS

SELECT name
FROM employees e
WHERE EXISTS (
    SELECT 1
    FROM departments d
    WHERE e.department_id = d.department_id
);

## NOT EXISTS

SELECT name
FROM employees e
WHERE NOT EXISTS (
    SELECT 1
    FROM departments d
    WHERE e.department_id = d.department_id
);

## EXISTS with Condition

SELECT name, salary
FROM employees e
WHERE EXISTS (
    SELECT 1
    FROM departments d
    WHERE e.department_id = d.department_id
    AND d.location = 'Pune'
);