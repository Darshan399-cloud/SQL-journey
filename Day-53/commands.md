# Day 53 - Database Setup

CREATE DATABASE day53_practice;
USE day53_practice;

CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(50)
);

INSERT INTO departments VALUES
(1, 'IT'),
(2, 'HR'),
(3, 'Finance'),
(4, 'Sales'),
(5, 'Marketing');

CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    salary DECIMAL(10,2),
    department_id INT,
    FOREIGN KEY (department_id)
        REFERENCES departments(department_id)
);

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

SELECT * FROM employees;
SELECT * FROM departments;