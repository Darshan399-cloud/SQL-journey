# SQL String Function Commands

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    city VARCHAR(100)
);

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 'IT', 'Nandurbar');

INSERT INTO employees
VALUES (102, 'Rahul', 'IT', 'Pune');

INSERT INTO employees
VALUES (103, 'Amit', 'HR', 'Mumbai');

INSERT INTO employees
VALUES (104, 'Priya', 'Finance', 'Nashik');

INSERT INTO employees
VALUES (105, 'Sneha', 'HR', 'Pune');

## CONCAT

SELECT
    CONCAT(name, ' - ', department) AS employee_details
FROM employees;

## UPPER

SELECT
    UPPER(name) AS uppercase_name
FROM employees;

## LOWER

SELECT
    LOWER(name) AS lowercase_name
FROM employees;

## LENGTH

SELECT
    name,
    LENGTH(name) AS name_length
FROM employees;

## TRIM

SELECT
    TRIM(name) AS cleaned_name
FROM employees;

## SUBSTRING

SELECT
    name,
    SUBSTRING(name, 1, 3) AS short_name
FROM employees;

## REPLACE

SELECT
    name,
    REPLACE(name, 'a', '@') AS modified_name
FROM employees;

## Multiple Functions

SELECT
    UPPER(TRIM(name)) AS formatted_name
FROM employees;

## String Function with WHERE

SELECT
    name,
    city
FROM employees
WHERE LENGTH(name) > 5;