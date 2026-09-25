# SQL Constraints

Constraints are rules applied to table columns to control the type of data that can be stored.

## NOT NULL

NOT NULL prevents a column from storing NULL values.

Example:

name VARCHAR(100) NOT NULL

## UNIQUE

UNIQUE prevents duplicate values in a column.

Example:

email VARCHAR(150) UNIQUE

## PRIMARY KEY

PRIMARY KEY uniquely identifies each row in a table.

A PRIMARY KEY cannot contain NULL values.

Example:

employee_id INT PRIMARY KEY

## FOREIGN KEY

FOREIGN KEY creates a relationship between two tables.

Example:

department_id INT,
FOREIGN KEY (department_id)
REFERENCES departments(department_id)

## CHECK

CHECK ensures that a value satisfies a specified condition.

Example:

salary DECIMAL(10,2) CHECK (salary > 0)

## DEFAULT

DEFAULT provides a value automatically when no value is specified.

Example:

status VARCHAR(20) DEFAULT 'Active'