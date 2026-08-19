# SQL UPDATE Commands

## Update Salary

UPDATE employees
SET salary = 60000
WHERE id = 1;

## Update Department

UPDATE employees
SET department = 'IT'
WHERE id = 2;

## Update Multiple Columns

UPDATE employees
SET department = 'Finance',
    salary = 65000
WHERE id = 3;

## Update Using Name

UPDATE employees
SET salary = 55000
WHERE name = 'Rahul';

## View Updated Data

SELECT * FROM employees;
