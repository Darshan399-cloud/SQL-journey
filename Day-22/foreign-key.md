# SQL FOREIGN KEY

A FOREIGN KEY is used to connect two tables.

It refers to the PRIMARY KEY of another table.

## Parent Table

CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(100)
);

## Child Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id)
        REFERENCES departments(department_id)
);

## Insert Parent Records

INSERT INTO departments
VALUES (1, 'IT');

INSERT INTO departments
VALUES (2, 'HR');

## Insert Child Records

INSERT INTO employees
VALUES (101, 'Darshan', 1);

INSERT INTO employees
VALUES (102, 'Rahul', 2);

## Referential Integrity

A FOREIGN KEY ensures that the value in the child table matches an existing value in the parent table.