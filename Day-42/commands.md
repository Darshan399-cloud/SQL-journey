# SQL User Management Commands

## Create User

CREATE USER 'student'@'localhost'
IDENTIFIED BY 'Student@123';

## Create Another User

CREATE USER 'developer'@'localhost'
IDENTIFIED BY 'Developer@123';

## Create Database

CREATE DATABASE company_db;

## Use Database

USE company_db;

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    salary DECIMAL(10,2)
);

## Grant SELECT

GRANT SELECT
ON company_db.employees
TO 'student'@'localhost';

## Grant Multiple Privileges

GRANT SELECT, INSERT, UPDATE
ON company_db.employees
TO 'developer'@'localhost';

## Grant All Privileges

GRANT ALL PRIVILEGES
ON company_db.*
TO 'developer'@'localhost';

## Show User Privileges

SHOW GRANTS
FOR 'student'@'localhost';

## Revoke INSERT

REVOKE INSERT
ON company_db.employees
FROM 'developer'@'localhost';

## Revoke UPDATE

REVOKE UPDATE
ON company_db.employees
FROM 'developer'@'localhost';

## Change Password

ALTER USER 'student'@'localhost'
IDENTIFIED BY 'NewStudent@123';

## Delete User

DROP USER 'student'@'localhost';

## Delete Another User

DROP USER 'developer'@'localhost';