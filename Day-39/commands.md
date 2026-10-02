# SQL Trigger Commands

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    salary DECIMAL(10,2)
);

## Create Employee Logs Table

CREATE TABLE employee_logs (
    employee_id INT,
    action VARCHAR(50)
);

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 'IT', 50000);

INSERT INTO employees
VALUES (102, 'Rahul', 'HR', 60000);

## BEFORE INSERT Trigger

DELIMITER //

CREATE TRIGGER before_employee_insert
BEFORE INSERT ON employees
FOR EACH ROW
BEGIN
    SET NEW.name = UPPER(NEW.name);
END //

DELIMITER ;

## Test BEFORE INSERT Trigger

INSERT INTO employees
VALUES (103, 'amit', 'Finance', 55000);

SELECT *
FROM employees;

## AFTER INSERT Trigger

DELIMITER //

CREATE TRIGGER after_employee_insert
AFTER INSERT ON employees
FOR EACH ROW
BEGIN
    INSERT INTO employee_logs
    VALUES (NEW.employee_id, 'INSERT');
END //

DELIMITER ;

## Test AFTER INSERT Trigger

INSERT INTO employees
VALUES (104, 'Priya', 'IT', 70000);

## Display Logs

SELECT *
FROM employee_logs;

## BEFORE UPDATE Trigger

DELIMITER //

CREATE TRIGGER before_employee_update
BEFORE UPDATE ON employees
FOR EACH ROW
BEGIN
    SET NEW.name = UPPER(NEW.name);
END //

DELIMITER ;

## Test UPDATE Trigger

UPDATE employees
SET name = 'rahul'
WHERE employee_id = 102;

## Display Employees

SELECT *
FROM employees;

## Show Triggers

SHOW TRIGGERS;

## Drop Trigger

DROP TRIGGER before_employee_insert;