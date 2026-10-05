# SQL Privileges

Privileges define what operations a database user is allowed to perform.

## Common Privileges

- SELECT
- INSERT
- UPDATE
- DELETE
- CREATE
- DROP
- ALTER
- ALL PRIVILEGES

## GRANT

GRANT is used to give privileges to a user.

## Example

GRANT SELECT
ON company_db.employees
TO 'student'@'localhost';

This allows the user to read data from the employees table.

## Multiple Privileges

GRANT SELECT, INSERT, UPDATE
ON company_db.employees
TO 'student'@'localhost';

## ALL PRIVILEGES

GRANT ALL PRIVILEGES
ON company_db.*
TO 'student'@'localhost';

This gives the user all available privileges on the company_db database.

## REVOKE

REVOKE removes previously granted privileges.

Example:

REVOKE INSERT
ON company_db.employees
FROM 'student'@'localhost';

## Show Privileges

SHOW GRANTS
FOR 'student'@'localhost';

## Important

GRANT gives permission.

REVOKE removes permission.