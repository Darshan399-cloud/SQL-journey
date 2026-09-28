# SQL Date and Time Operations

## Extract Year

SELECT
    YEAR(join_date) AS joining_year
FROM employees;

## Extract Month

SELECT
    MONTH(join_date) AS joining_month
FROM employees;

## Extract Day

SELECT
    DAY(join_date) AS joining_day
FROM employees;

## Format Date

SELECT
    DATE_FORMAT(join_date, '%d-%m-%Y') AS formatted_date
FROM employees;

## Find Employees Joined in 2026

SELECT
    name,
    join_date
FROM employees
WHERE YEAR(join_date) = 2026;

## Find Employees Joined in September

SELECT
    name,
    join_date
FROM employees
WHERE MONTH(join_date) = 9;

## Compare Dates

SELECT
    name,
    join_date
FROM employees
WHERE join_date > '2025-01-01';

## Order by Date

SELECT
    name,
    join_date
FROM employees
ORDER BY join_date;