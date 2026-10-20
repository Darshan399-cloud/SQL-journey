# Day 52 - SQL Practice Database

## 1. Create Database

CREATE DATABASE day52_practice;
USE day52_practice;

## 2. Create Departments Table

CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(50)
);

## 3. Insert Departments

INSERT INTO departments VALUES
(1, 'IT'),
(2, 'HR'),
(3, 'Finance'),
(4, 'Sales'),
(5, 'Marketing');

## 4. Create Employees Table

CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    salary DECIMAL(10,2),
    department_id INT,
    FOREIGN KEY (department_id)
        REFERENCES departments(department_id)
);

## 5. Insert Employees

INSERT INTO employees VALUES
(1, 'Amit', 60000, 1),
(2, 'Priya', 45000, 2),
(3, 'Rahul', 75000, 1),
(4, 'Sneha', 50000, 3),
(5, 'Vijay', 35000, 4),
(6, 'Neha', 60000, 1),
(7, 'Karan', 40000, NULL),
(8, 'Anita', 55000, 3),
(9, 'Rohan', 75000, 2),
(10, 'Meena', 30000, NULL);

## 6. Check Data

SELECT * FROM employees;
SELECT * FROM departments;

## 7. Test a Subquery

SELECT *
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

## 8. Test a CTE

WITH department_totals AS (
    SELECT department_id, COUNT(*) AS total
    FROM employees
    GROUP BY department_id
)
SELECT *
FROM department_totals;