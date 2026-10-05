# SQL User Management

Database User Management is used to control who can access a database and what operations they can perform.

## CREATE USER

CREATE USER is used to create a new database user.

## Syntax

CREATE USER 'username'@'localhost'
IDENTIFIED BY 'password';

## Example

CREATE USER 'student'@'localhost'
IDENTIFIED BY 'Student@123';

## DROP USER

DROP USER is used to delete a database user.

Example:

DROP USER 'student'@'localhost';

## ALTER USER

ALTER USER can be used to change user settings such as password.

Example:

ALTER USER 'student'@'localhost'
IDENTIFIED BY 'NewPassword@123';

## Important

Database users and database tables are different.

A user is given permissions to perform specific operations on databases and tables.