# Creating and Managing SQL Views

## CREATE VIEW

CREATE VIEW employee_details AS
SELECT
    name,
    department,
    salary
FROM employees;

## SELECT from View

SELECT *
FROM employee_details;

## SELECT Specific Columns

SELECT name, salary
FROM employee_details;

## CREATE OR REPLACE VIEW

CREATE OR REPLACE VIEW employee_details AS
SELECT
    name,
    department
FROM employees;

## DROP VIEW

DROP VIEW employee_details;

## View with JOIN

CREATE VIEW employee_department AS
SELECT
    employees.name,
    departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;

## Query JOIN View

SELECT *
FROM employee_department;

## Important

A View is based on a SELECT query.

When the underlying table data changes, the View normally reflects those changes when queried.