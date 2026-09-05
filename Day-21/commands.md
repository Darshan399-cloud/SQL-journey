# SQL Constraint Commands

## NOT NULL

CREATE TABLE students (
    id INT,
    name VARCHAR(100) NOT NULL
);

## UNIQUE

CREATE TABLE users (
    id INT,
    email VARCHAR(100) UNIQUE
);

## PRIMARY KEY

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100)
);

## DEFAULT

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    city VARCHAR(50) DEFAULT 'Pune'
);

## CHECK

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT CHECK (age >= 18)
);

## Multiple Constraints

CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    age INT CHECK (age >= 18),
    city VARCHAR(50) DEFAULT 'Pune'
);