# UPDATE Statement

UPDATE is used to modify existing records in a table.

## UPDATE Syntax

UPDATE table_name
SET column_name = value
WHERE condition;

## Update Single Column

UPDATE employees
SET salary = 60000
WHERE id = 1;

## Update Multiple Columns

UPDATE employees
SET department = 'Finance',
    salary = 65000
WHERE id = 2;

## Update Department

UPDATE employees
SET department = 'IT'
WHERE id = 3;