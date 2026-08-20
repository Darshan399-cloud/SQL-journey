# SQL DELETE Commands

## Delete by ID

DELETE FROM employees
WHERE id = 1;

## Delete by Name

DELETE FROM employees
WHERE name = 'Rahul';

## Delete by Department

DELETE FROM employees
WHERE department = 'HR';

## Delete by Salary

DELETE FROM employees
WHERE salary < 30000;

## View Remaining Records

SELECT * FROM employees;