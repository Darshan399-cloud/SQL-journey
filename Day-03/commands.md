
# SQL INSERT Commands

## Insert Single Record

INSERT INTO employees
VALUES (1, 'Rahul', 'IT', 50000);

## Insert Multiple Records

INSERT INTO employees
VALUES
(2, 'Amit', 'HR', 45000),
(3, 'Priya', 'Finance', 55000);

## Insert Specific Columns

INSERT INTO employees (id, name, department)
VALUES (4, 'Rohit', 'IT');

## View Inserted Data

SELECT * FROM employees;