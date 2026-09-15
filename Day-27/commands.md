# SQL Subquery Commands

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    salary DECIMAL(10,2)
);

## Insert Records

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

## Display All Employees

SELECT * FROM employees;

## Find Average Salary

SELECT AVG(salary)
FROM employees;

## Employees with Salary Greater Than Average

SELECT name, salary
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

## Employee with Highest Salary

SELECT name, salary
FROM employees
WHERE salary = (
    SELECT MAX(salary)
    FROM employees
);

## Employee with Lowest Salary

SELECT name, salary
FROM employees
WHERE salary = (
    SELECT MIN(salary)
    FROM employees
);

## Employees Earning Less Than Average

SELECT name, salary
FROM employees
WHERE salary < (
    SELECT AVG(salary)
    FROM employees
);

## Find Employees with Same Salary as a Specific Employee

SELECT name, salary
FROM employees
WHERE salary = (
    SELECT salary
    FROM employees
    WHERE name = 'Rahul'
);