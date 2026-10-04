# SQL Cursor Commands

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

## Create Cursor Procedure

DELIMITER //

CREATE PROCEDURE process_employees()
BEGIN

    DECLARE employee_name VARCHAR(100);
    DECLARE finished INT DEFAULT 0;

    DECLARE employee_cursor CURSOR FOR
        SELECT name
        FROM employees;

    DECLARE CONTINUE HANDLER
        FOR NOT FOUND SET finished = 1;

    OPEN employee_cursor;

    employee_loop: LOOP

        FETCH employee_cursor
        INTO employee_name;

        IF finished = 1 THEN
            LEAVE employee_loop;
        END IF;

        SELECT employee_name;

    END LOOP;

    CLOSE employee_cursor;

END //

DELIMITER ;

## Execute Procedure

CALL process_employees();

## Create Salary Cursor Procedure

DELIMITER //

CREATE PROCEDURE process_salaries()
BEGIN

    DECLARE employee_salary DECIMAL(10,2);
    DECLARE finished INT DEFAULT 0;

    DECLARE salary_cursor CURSOR FOR
        SELECT salary
        FROM employees;

    DECLARE CONTINUE HANDLER
        FOR NOT FOUND SET finished = 1;

    OPEN salary_cursor;

    salary_loop: LOOP

        FETCH salary_cursor
        INTO employee_salary;

        IF finished = 1 THEN
            LEAVE salary_loop;
        END IF;

        SELECT employee_salary;

    END LOOP;

    CLOSE salary_cursor;

END //

DELIMITER ;

## Execute Salary Procedure

CALL process_salaries();

## Show Procedures

SHOW PROCEDURE STATUS
WHERE Db = DATABASE();

## Drop Procedure

DROP PROCEDURE process_employees;

DROP PROCEDURE process_salaries;