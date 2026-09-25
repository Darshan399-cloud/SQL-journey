# PRIMARY KEY and FOREIGN KEY

## PRIMARY KEY

A PRIMARY KEY uniquely identifies every record in a table.

Example:

CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(100)
);

## FOREIGN KEY

A FOREIGN KEY references a PRIMARY KEY or UNIQUE key in another table.

Example:

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id)
        REFERENCES departments(department_id)
);

## Relationship

departments
    |
    | department_id
    |
employees
    |
    | department_id

The department_id in employees references department_id in departments.

## Important

PRIMARY KEY identifies records in its own table.

FOREIGN KEY creates a relationship with another table.