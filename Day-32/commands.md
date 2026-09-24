# SQL Transaction Commands

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    salary DECIMAL(10,2)
);

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 'IT', 50000);

INSERT INTO employees
VALUES (102, 'Rahul', 'HR', 60000);

INSERT INTO employees
VALUES (103, 'Amit', 'Finance', 55000);

## Start Transaction

START TRANSACTION;

## Update Employee

UPDATE employees
SET salary = 65000
WHERE employee_id = 101;

## Commit Transaction

COMMIT;

## Start New Transaction

START TRANSACTION;

## Update Employee

UPDATE employees
SET salary = 70000
WHERE employee_id = 102;

## Rollback Transaction

ROLLBACK;

## Start Transaction with SAVEPOINT

START TRANSACTION;

UPDATE employees
SET salary = 60000
WHERE employee_id = 101;

SAVEPOINT salary_update;

UPDATE employees
SET salary = 75000
WHERE employee_id = 102;

ROLLBACK TO SAVEPOINT salary_update;

COMMIT;

## Display Employees

SELECT *
FROM employees;