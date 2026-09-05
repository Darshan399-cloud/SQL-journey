# SQL Constraints

SQL Constraints are rules used to control the data stored in a table.

## NOT NULL

NOT NULL prevents a column from storing NULL values.

CREATE TABLE students (
    id INT,
    name VARCHAR(100) NOT NULL
);

## UNIQUE

UNIQUE ensures that all values in a column are different.

CREATE TABLE students (
    id INT,
    email VARCHAR(100) UNIQUE
);

## PRIMARY KEY

PRIMARY KEY uniquely identifies each record in a table.

CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(100)
);

## DEFAULT

DEFAULT assigns a value when no value is provided.

CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    city VARCHAR(50) DEFAULT 'Pune'
);

## CHECK

CHECK is used to restrict values based on a condition.

CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT CHECK (age >= 18)
);