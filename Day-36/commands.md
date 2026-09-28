# SQL Date and Time Commands

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    join_date DATE
);

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 'IT', '2024-06-15');

INSERT INTO employees
VALUES (102, 'Rahul', 'IT', '2025-01-20');

INSERT INTO employees
VALUES (103, 'Amit', 'HR', '2025-09-10');

INSERT INTO employees
VALUES (104, 'Priya', 'Finance', '2026-03-25');

INSERT INTO employees
VALUES (105, 'Sneha', 'HR', '2026-09-05');

## Current Date

SELECT CURRENT_DATE();

## Current Time

SELECT CURRENT_TIME();

## Current Date and Time

SELECT NOW();

## Extract Year

SELECT
    name,
    YEAR(join_date) AS joining_year
FROM employees;

## Extract Month

SELECT
    name,
    MONTH(join_date) AS joining_month
FROM employees;

## Extract Day

SELECT
    name,
    DAY(join_date) AS joining_day
FROM employees;

## Format Date

SELECT
    name,
    DATE_FORMAT(join_date, '%d-%m-%Y') AS formatted_date
FROM employees;

## Employees Joined in 2026

SELECT
    name,
    join_date
FROM employees
WHERE YEAR(join_date) = 2026;

## Employees Joined After 2025

SELECT
    name,
    join_date
FROM employees
WHERE join_date > '2025-01-01';

## Sort by Joining Date

SELECT
    name,
    join_date
FROM employees
ORDER BY join_date;