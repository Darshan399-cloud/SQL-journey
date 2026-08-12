
# INSERT INTO

INSERT INTO is used to add new records into a table.

## INSERT INTO Syntax

INSERT INTO table_name
VALUES (value1, value2, value3);

## Insert Single Record

INSERT INTO employees
VALUES (1, 'Rahul', 'IT', 50000);

## Insert Multiple Records

INSERT INTO employees
VALUES
(2, 'Amit', 'HR', 45000),
(3, 'Priya', 'Finance', 55000);

## Insert Data into Specific Columns

INSERT INTO employees (id, name, department)
VALUES (4, 'Rohit', 'IT');