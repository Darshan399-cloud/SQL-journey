# SQL Triggers

A Trigger is a database object that automatically executes when a specific event occurs on a table.

Triggers can execute automatically when:

- INSERT
- UPDATE
- DELETE

## Basic Syntax

DELIMITER //

CREATE TRIGGER trigger_name
AFTER INSERT ON table_name
FOR EACH ROW
BEGIN
    SQL statements;
END //

DELIMITER ;

## AFTER INSERT Trigger

This Trigger runs automatically after a new record is inserted.

Example:

DELIMITER //

CREATE TRIGGER after_employee_insert
AFTER INSERT ON employees
FOR EACH ROW
BEGIN
    INSERT INTO employee_logs
    VALUES (NEW.employee_id, 'Employee Added');
END //

DELIMITER ;

## OLD and NEW

NEW refers to the new value of a record.

OLD refers to the previous value of a record.

## Example

NEW.salary

This represents the new salary value.

OLD.salary

This represents the previous salary value.

## Important

Triggers execute automatically.

We do not need to use CALL like Stored Procedures.