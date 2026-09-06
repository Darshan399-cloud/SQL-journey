# SQL Table Relationships

Relationships are used to connect data between tables.

## One-to-Many Relationship

One department can have many employees.

Example:

Department
    |
    |--- Employee 1
    |--- Employee 2
    |--- Employee 3

## Parent Table

departments

department_id
department_name

## Child Table

employees

employee_id
name
department_id

The department_id in employees is a FOREIGN KEY.

## Example

CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(100)
);

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id)
        REFERENCES departments(department_id)
);