# SQL FOREIGN KEY Commands

## Create Parent Table

CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(100)
);

## Create Child Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id)
        REFERENCES departments(department_id)
);

## Insert Department

INSERT INTO departments
VALUES (1, 'IT');

INSERT INTO departments
VALUES (2, 'HR');

## Insert Employee

INSERT INTO employees
VALUES (101, 'Darshan', 1);

INSERT INTO employees
VALUES (102, 'Rahul', 2);

## View Departments

SELECT * FROM departments;

## View Employees

SELECT * FROM employees;

## Add FOREIGN KEY to Existing Table

ALTER TABLE employees
ADD FOREIGN KEY (department_id)
REFERENCES departments(department_id);