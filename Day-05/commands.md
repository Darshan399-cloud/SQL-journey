# SQL WHERE Commands

## Equal To

SELECT *
FROM employees
WHERE id = 1;

## Greater Than

SELECT *
FROM employees
WHERE salary > 50000;

## Less Than

SELECT *
FROM employees
WHERE salary < 50000;

## Greater Than or Equal To

SELECT *
FROM employees
WHERE salary >= 50000;

## Less Than or Equal To

SELECT *
FROM employees
WHERE salary <= 50000;

## Not Equal To

SELECT *
FROM employees
WHERE department <> 'HR';

## AND

SELECT *
FROM employees
WHERE department = 'IT' AND salary > 50000;

## OR

SELECT *
FROM employees
WHERE department = 'IT' OR department = 'HR';

## NOT

SELECT *
FROM employees
WHERE NOT department = 'HR';