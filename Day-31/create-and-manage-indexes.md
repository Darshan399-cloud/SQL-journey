# Creating and Managing SQL Indexes

## Create Index

CREATE INDEX idx_employee_name
ON employees (name);

## Create Index on Department

CREATE INDEX idx_employee_department
ON employees (department);

## Create Unique Index

CREATE UNIQUE INDEX idx_employee_email
ON employees (email);

## Create Composite Index

CREATE INDEX idx_department_salary
ON employees (department, salary);

## Show Indexes in MySQL

SHOW INDEX FROM employees;

## Drop Index

DROP INDEX idx_employee_name
ON employees;

## Drop Composite Index

DROP INDEX idx_department_salary
ON employees;

## Important

The order of columns in a composite Index matters.

For example:

CREATE INDEX idx_department_salary
ON employees (department, salary);

This Index starts with department and then salary.