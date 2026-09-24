# SQL Transactions

A transaction is a sequence of one or more SQL operations treated as a single unit of work.

A transaction can be permanently saved using COMMIT or undone using ROLLBACK.

## Why Transactions are Used?

Transactions help maintain data consistency and reliability.

## COMMIT

COMMIT permanently saves the changes made during a transaction.

Example:

START TRANSACTION;

UPDATE employees
SET salary = 60000
WHERE employee_id = 101;

COMMIT;

## ROLLBACK

ROLLBACK cancels changes made during the current transaction that have not been committed.

Example:

START TRANSACTION;

UPDATE employees
SET salary = 70000
WHERE employee_id = 101;

ROLLBACK;

The salary change is undone.

## SAVEPOINT

SAVEPOINT creates a point inside a transaction to which you can later roll back.

Example:

START TRANSACTION;

UPDATE employees
SET salary = 60000
WHERE employee_id = 101;

SAVEPOINT salary_update;

UPDATE employees
SET salary = 70000
WHERE employee_id = 102;

ROLLBACK TO SAVEPOINT salary_update;

COMMIT;

The second UPDATE is undone, while the first UPDATE remains part of the transaction.

## Transaction Flow

START TRANSACTION
        |
        
    SQL Operations
        |
        
COMMIT or ROLLBACK