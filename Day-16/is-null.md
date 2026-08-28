# IS NULL and IS NOT NULL

## Find NULL Values

SELECT *
FROM employees
WHERE salary IS NULL;

## Find Non-NULL Values

SELECT *
FROM employees
WHERE salary IS NOT NULL;

## NULL with Multiple Conditions

SELECT *
FROM employees
WHERE department IS NULL
AND salary IS NULL;

## NOT NULL with Multiple Conditions

SELECT *
FROM employees
WHERE department IS NOT NULL
AND salary IS NOT NULL;

## COUNT with NULL

SELECT COUNT(department)
FROM employees;

COUNT(column_name) does not count NULL values.

## COUNT All Records

SELECT COUNT(*)
FROM employees;

COUNT(*) counts all records.