# SQL Stored Procedure Commands

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
VALUES (102, 'Rahul', 'IT', 65000);

INSERT INTO employees
VALUES (103, 'Amit', 'HR', 45000);

INSERT INTO employees
VALUES (104, 'Priya', 'Finance', 70000);

INSERT INTO employees
VALUES (105, 'Sneha', 'HR', 55000);

## Create Basic Procedure

DELIMITER //

CREATE PROCEDURE get_all_employees()
BEGIN
    SELECT *
    FROM employees;
END //

DELIMITER ;

## Call Procedure

CALL get_all_employees();

## Create Procedure with IN Parameter

DELIMITER //

CREATE PROCEDURE get_by_department(
    IN dept_name VARCHAR(100)
)
BEGIN
    SELECT *
    FROM employees
    WHERE department = dept_name;
END //

DELIMITER ;

## Call Procedure

CALL get_by_department('IT');

## Create Salary Procedure

DELIMITER //

CREATE PROCEDURE get_by_salary(
    IN min_salary DECIMAL(10,2)
)
BEGIN
    SELECT *
    FROM employees
    WHERE salary >= min_salary;
END //

DELIMITER ;

## Call Procedure

CALL get_by_salary(60000);

## Create OUT Procedure

DELIMITER //

CREATE PROCEDURE employee_count(
    OUT total INT
)
BEGIN
    SELECT COUNT(*)
    INTO total
    FROM employees;
END //

DELIMITER ;

## Call OUT Procedure

CALL employee_count(@total);

SELECT @total;

## Show Procedures

SHOW PROCEDURE STATUS
WHERE Db = DATABASE();

## Drop Procedure

DROP PROCEDURE get_all_employees;