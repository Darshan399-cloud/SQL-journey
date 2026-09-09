# SQL JOIN Commands

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
    FOREIGN KEY (department_id)
        REFERENCES departments(department_id)
);

## Insert Departments

INSERT INTO departments
VALUES (1, 'IT');

INSERT INTO departments
VALUES (2, 'HR');

INSERT INTO departments
VALUES (3, 'Finance');

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 1);

INSERT INTO employees
VALUES (102, 'Rahul', 2);

INSERT INTO employees
VALUES (103, 'Amit', 3);

## INNER JOIN

SELECT
    employees.name,
    departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;

## JOIN with SELECT *

SELECT *
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;

## JOIN with WHERE

SELECT
    employees.name,
    departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id
WHERE departments.department_name = 'IT';