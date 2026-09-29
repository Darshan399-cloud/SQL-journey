# SQL NULL Function Commands

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(150),
    phone VARCHAR(20),
    manager_id INT,
    salary DECIMAL(10,2)
);

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 'darshan@example.com', '9876543210', NULL, 50000);

INSERT INTO employees
VALUES (102, 'Rahul', 'rahul@example.com', NULL, 101, 60000);

INSERT INTO employees
VALUES (103, 'Amit', NULL, '9876500000', 101, 55000);

INSERT INTO employees
VALUES (104, 'Priya', 'priya@example.com', NULL, 102, 70000);

INSERT INTO employees
VALUES (105, 'Sneha', NULL, NULL, 102, 45000);

## Find NULL Manager

SELECT *
FROM employees
WHERE manager_id IS NULL;

## Find Employees with a Manager

SELECT *
FROM employees
WHERE manager_id IS NOT NULL;

## IFNULL

SELECT
    name,
    IFNULL(phone, 'Not Available') AS phone
FROM employees;

## IFNULL with Email

SELECT
    name,
    IFNULL(email, 'No Email') AS email
FROM employees;

## COALESCE

SELECT
    name,
    COALESCE(phone, email, 'No Contact') AS contact
FROM employees;

## COALESCE with Salary

SELECT
    name,
    COALESCE(salary, 0) AS salary
FROM employees;

## NULLIF

SELECT NULLIF(10, 10);

SELECT NULLIF(10, 20);

## Count Non-NULL Emails

SELECT COUNT(email)
FROM employees;

## Count All Employees

SELECT COUNT(*)
FROM employees;