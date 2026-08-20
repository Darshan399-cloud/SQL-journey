# DELETE Conditions

## DELETE with WHERE

DELETE FROM employees
WHERE salary < 30000;

## Delete Multiple Records

DELETE FROM employees
WHERE department = 'HR';

## DELETE without WHERE

DELETE FROM employees;

This deletes all records from the table.

## Safe DELETE

Always use WHERE when you want to delete specific records.

Example:

DELETE FROM employees
WHERE id = 5;