# BEFORE and AFTER Triggers

## BEFORE INSERT

BEFORE INSERT runs before a new record is inserted.

Example:

DELIMITER //

CREATE TRIGGER before_employee_insert
BEFORE INSERT ON employees
FOR EACH ROW
BEGIN
    SET NEW.name = UPPER(NEW.name);
END //

DELIMITER ;

This converts the employee name to uppercase before inserting.

## AFTER INSERT

AFTER INSERT runs after a record is inserted.

Example:

DELIMITER //

CREATE TRIGGER after_employee_insert
AFTER INSERT ON employees
FOR EACH ROW
BEGIN
    INSERT INTO employee_logs
    VALUES (NEW.employee_id, 'INSERT');
END //

DELIMITER ;

## BEFORE UPDATE

BEFORE UPDATE runs before an existing record is updated.

Example:

DELIMITER //

CREATE TRIGGER before_employee_update
BEFORE UPDATE ON employees
FOR EACH ROW
BEGIN
    SET NEW.name = UPPER(NEW.name);
END //

DELIMITER ;

## AFTER UPDATE

AFTER UPDATE runs after an existing record is updated.

## BEFORE DELETE

BEFORE DELETE runs before a record is deleted.

## AFTER DELETE

AFTER DELETE runs after a record is deleted.

For DELETE triggers, OLD values can be used.

Example:

OLD.employee_id

## Important

INSERT:
NEW values are available.

UPDATE:
OLD and NEW values are available.

DELETE:
OLD values are available.