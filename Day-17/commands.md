# SQL String Function Commands

## Convert Names to Uppercase

SELECT UPPER(name)
FROM employees;

## Convert Names to Lowercase

SELECT LOWER(name)
FROM employees;

## Find Name Length

SELECT name, LENGTH(name)
FROM employees;

## Combine Name and Department

SELECT CONCAT(name, ' - ', department)
FROM employees;

## Extract First Three Characters

SELECT SUBSTRING(name, 1, 3)
FROM employees;

## Remove Spaces

SELECT TRIM(name)
FROM employees;

## Use Alias with String Function

SELECT UPPER(name) AS employee_name
FROM employees;