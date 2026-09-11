# SQL FULL OUTER JOIN and SELF JOIN Commands

## Create Departments Table

CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(100)
);

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department_id INT,
    manager_id INT
);

## Insert Departments

INSERT INTO departments
VALUES (1, 'IT');

INSERT INTO departments
VALUES (2, 'HR');

INSERT INTO departments
VALUES (3, 'Finance');

INSERT INTO departments
VALUES (4, 'Marketing');

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 1, NULL);

INSERT INTO employees
VALUES (102, 'Rahul', 1, 101);

INSERT INTO employees
VALUES (103, 'Amit', 2, 101);

## FULL OUTER JOIN Simulation in MySQL

SELECT
    employees.name,
    departments.department_name
FROM employees
LEFT JOIN departments
ON employees.department_id = departments.department_id

UNION

SELECT
    employees.name,
    departments.department_name
FROM employees
RIGHT JOIN departments
ON employees.department_id = departments.department_id;

## SELF JOIN

SELECT
    e.name AS employee,
    m.name AS manager
FROM employees e
LEFT JOIN employees m
ON e.manager_id = m.employee_id;

## Display Employee and Manager

SELECT
    e.employee_id,
    e.name AS employee_name,
    m.name AS manager_name
FROM employees e
LEFT JOIN employees m
ON e.manager_id = m.employee_id;