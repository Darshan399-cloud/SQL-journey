# SQL Constraints Commands

## Create Departments Table

CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(100) NOT NULL UNIQUE
);

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(150) UNIQUE,
    department_id INT,
    salary DECIMAL(10,2) CHECK (salary > 0),
    status VARCHAR(20) DEFAULT 'Active',
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
(employee_id, name, email, department_id, salary)
VALUES
(101, 'Darshan', 'darshan@example.com', 1, 50000);

## Insert Employee with DEFAULT

INSERT INTO employees
(employee_id, name, email, department_id, salary)
VALUES
(102, 'Rahul', 'rahul@example.com', 2, 60000);

## Display Employees

SELECT *
FROM employees;

## Display Departments

SELECT *
FROM departments;

## Check Table Structure

DESC employees;

DESC departments;