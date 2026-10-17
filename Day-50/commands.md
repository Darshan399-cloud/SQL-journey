# SQL Practice Database Setup

## 1. Create Database

CREATE DATABASE sql_practice;
USE sql_practice;

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
(4, 'Sales');

## 4. Create Employees Table

CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    email VARCHAR(100),
    salary DECIMAL(10,2),
    department_id INT,
    FOREIGN KEY (department_id)
        REFERENCES departments(department_id)
);

## 5. Insert Employees

INSERT INTO employees VALUES
(1, 'Amit', 'amit@example.com', 60000, 1),
(2, 'Priya', 'priya@example.com', 45000, 2),
(3, 'Rahul', 'rahul@example.com', 75000, 1),
(4, 'Sneha', 'sneha@example.com', 50000, 3),
(5, 'Vijay', 'vijay@example.com', 35000, 4),
(6, 'Neha', 'neha@example.com', 60000, 1),
(7, 'Karan', 'karan@example.com', 40000, NULL),
(8, 'Anita', 'anita@example.com', 55000, 3);

## 6. Check the Data

SELECT * FROM departments;
SELECT * FROM employees;

## 7. Practice JOIN

SELECT e.name, e.salary, d.department_name
FROM employees e
LEFT JOIN departments d
ON e.department_id = d.department_id;

## 8. Practice GROUP BY

SELECT department_id, COUNT(*) AS total_employees
FROM employees
GROUP BY department_id;

## 9. Practice HAVING

SELECT department_id, AVG(salary) AS average_salary
FROM employees
GROUP BY department_id
HAVING AVG(salary) > 50000;

## 10. Practice UPDATE

UPDATE employees
SET salary = 65000
WHERE id = 1;

## 11. Practice DELETE

DELETE FROM employees
WHERE id = 5;