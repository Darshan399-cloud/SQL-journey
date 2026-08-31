# String Function Examples

## UPPER()

SELECT UPPER(name) AS employee_name
FROM employees;

## LOWER()

SELECT LOWER(name) AS employee_name
FROM employees;

## LENGTH()

SELECT name, LENGTH(name) AS name_length
FROM employees;

## CONCAT()

SELECT CONCAT(name, ' works in ', department) AS employee_details
FROM employees;

## SUBSTRING()

SELECT SUBSTRING(name, 1, 3) AS short_name
FROM employees;

## TRIM()

SELECT TRIM(name) AS employee_name
FROM employees;

## String Functions with WHERE

SELECT *
FROM employees
WHERE UPPER(department) = 'IT';