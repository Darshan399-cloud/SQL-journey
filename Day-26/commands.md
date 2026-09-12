# SQL UNION and UNION ALL Commands

## Create First Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    city VARCHAR(100)
);

## Create Second Table

CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    name VARCHAR(100),
    city VARCHAR(100)
);

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 'Nandurbar');

INSERT INTO employees
VALUES (102, 'Rahul', 'Pune');

INSERT INTO employees
VALUES (103, 'Amit', 'Mumbai');

## Insert Customers

INSERT INTO customers
VALUES (201, 'Rahul', 'Pune');

INSERT INTO customers
VALUES (202, 'Priya', 'Nashik');

INSERT INTO customers
VALUES (203, 'Sneha', 'Mumbai');

## UNION

SELECT name, city
FROM employees

UNION

SELECT name, city
FROM customers;

## UNION ALL

SELECT name, city
FROM employees

UNION ALL

SELECT name, city
FROM customers;

## UNION with WHERE

SELECT name, city
FROM employees
WHERE city = 'Pune'

UNION

SELECT name, city
FROM customers
WHERE city = 'Pune';

## UNION ALL with WHERE

SELECT name, city
FROM employees
WHERE city = 'Mumbai'

UNION ALL

SELECT name, city
FROM customers
WHERE city = 'Mumbai';