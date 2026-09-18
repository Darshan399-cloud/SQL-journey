# SQL Views

A View is a virtual table based on the result of a SELECT query.

A View does not normally store the data separately. It displays data from the underlying tables.

## Why Use Views?

Views are useful for:

- Simplifying complex queries
- Reusing SQL queries
- Hiding unnecessary columns
- Providing controlled access to data
- Making reports easier to create

## Basic Syntax

CREATE VIEW view_name AS
SELECT column1, column2
FROM table_name
WHERE condition;

## Example

CREATE VIEW employee_details AS
SELECT
    name,
    department,
    salary
FROM employees;

## Display View

SELECT *
FROM employee_details;

## View with WHERE

CREATE VIEW high_salary_employees AS
SELECT
    name,
    department,
    salary
FROM employees
WHERE salary >= 60000;

## Query the View

SELECT *
FROM high_salary_employees;