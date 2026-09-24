# COMMIT, ROLLBACK and SAVEPOINT

## START TRANSACTION

Starts a new transaction.

START TRANSACTION;

## COMMIT

Permanently saves transaction changes.

COMMIT;

## ROLLBACK

Undoes uncommitted transaction changes.

ROLLBACK;

## SAVEPOINT

Creates a point inside a transaction.

SAVEPOINT savepoint_name;

## ROLLBACK TO SAVEPOINT

Rolls back changes made after the specified SAVEPOINT.

ROLLBACK TO SAVEPOINT savepoint_name;

## Example

START TRANSACTION;

INSERT INTO employees
VALUES (106, 'Kiran', 'IT', 55000);

SAVEPOINT employee_insert;

UPDATE employees
SET salary = 60000
WHERE employee_id = 106;

ROLLBACK TO SAVEPOINT employee_insert;

COMMIT;

## Important

COMMIT makes transaction changes permanent.

ROLLBACK cancels uncommitted changes.

SAVEPOINT allows partial rollback inside a transaction.