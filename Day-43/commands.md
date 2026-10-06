# SQL Backup and Restore Commands

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

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 'IT', 50000);

INSERT INTO employees
VALUES (102, 'Rahul', 'IT', 65000);

INSERT INTO employees
VALUES (103, 'Amit', 'HR', 45000);

INSERT INTO employees
VALUES (104, 'Priya', 'Finance', 70000);

## Display Data

SELECT *
FROM employees;

## Backup Complete Database

mysqldump -u root -p company_db > company_db_backup.sql

## Backup Only Employees Table

mysqldump -u root -p company_db employees > employees_backup.sql

## Backup Database Structure Only

mysqldump -u root -p --no-data company_db > company_structure.sql

## Backup Data Only

mysqldump -u root -p --no-create-info company_db > company_data.sql

## Restore Database

mysql -u root -p company_db < company_db_backup.sql

## Restore Using SOURCE

mysql -u root -p

CREATE DATABASE restored_db;

USE restored_db;

SOURCE company_db_backup.sql;

## Check Tables

SHOW TABLES;

## Check Restored Data

SELECT *
FROM employees;