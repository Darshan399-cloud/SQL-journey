# Primary Key

A Primary Key is used to uniquely identify each row in a table.

## Example

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    salary DECIMAL(10,2)
);

## Insert Data

INSERT INTO employees
VALUES (1, 'Darshan', 35000);

INSERT INTO employees
VALUES (2, 'Rahul', 40000);

## Duplicate Primary Key

The following query will produce an error because employee_id 1 already exists.

INSERT INTO employees
VALUES (1, 'Amit', 30000);

## Multiple Columns

A table can have only one PRIMARY KEY, but the primary key can contain multiple columns.

Example:

PRIMARY KEY (student_id, course_id)