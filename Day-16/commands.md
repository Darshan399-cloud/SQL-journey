# SQL NULL Commands
# SQL NULL Commands

## Find NULL Department

SELECT *
FROM employees
WHERE department IS NULL;

## Find Non-NULL Department

SELECT *
FROM employees
WHERE department IS NOT NULL;

## Find NULL Salary

SELECT *
FROM employees
WHERE salary IS NULL;

## Find Non-NULL Salary

SELECT *
FROM employees
WHERE salary IS NOT NULL;

## Count Non-NULL Departments

SELECT COUNT(department)
FROM employees;

## Count All Records

SELECT COUNT(*)
FROM employees;