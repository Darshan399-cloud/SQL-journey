# SQL String Functions - Advanced Examples

## CONCAT()

SELECT CONCAT(name, ' - ', department)
FROM employees;

## UPPER()

SELECT
    name,
    UPPER(name) AS uppercase_name
FROM employees;

## LOWER()

SELECT
    name,
    LOWER(name) AS lowercase_name
FROM employees;

## LENGTH()

SELECT
    name,
    LENGTH(name) AS name_length
FROM employees;

## TRIM()

SELECT
    TRIM(name) AS cleaned_name
FROM employees;

## SUBSTRING()

SELECT
    name,
    SUBSTRING(name, 1, 3) AS short_name
FROM employees;

## REPLACE()

SELECT
    name,
    REPLACE(name, 'a', '@') AS modified_name
FROM employees;

## Combine Multiple Functions

SELECT
    UPPER(TRIM(name)) AS formatted_name
FROM employees;

## String Function with WHERE

SELECT name
FROM employees
WHERE LENGTH(name) > 5;