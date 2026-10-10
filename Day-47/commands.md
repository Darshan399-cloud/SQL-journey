# SQL Data Type Commands

## Create Students Table

CREATE TABLE students (
    student_id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT,
    percentage DECIMAL(5,2),
    birth_date DATE,
    is_active BOOLEAN
);

## Insert Student Records

INSERT INTO students
VALUES
(101, 'Darshan', 22, 85.50, '2004-01-15', TRUE);

INSERT INTO students
VALUES
(102, 'Rahul', 23, 78.25, '2003-06-20', FALSE);

## Display Students

SELECT *
FROM students;

## Create Products Table

CREATE TABLE products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(150),
    price DECIMAL(10,2),
    description TEXT,
    created_at DATETIME
);

## Insert Products

INSERT INTO products
VALUES
(1, 'Keyboard', 799.99, 'Wireless keyboard', '2026-10-10 10:30:00');

INSERT INTO products
VALUES
(2, 'Mouse', 499.50, 'USB mouse', '2026-10-10 11:00:00');

## Display Products

SELECT *
FROM products;

## Check Table Structure

DESC students;

DESC products;

## Display Column Information

SHOW COLUMNS FROM students;

## Create Table with CHAR

CREATE TABLE countries (
    country_id INT PRIMARY KEY,
    country_code CHAR(2),
    country_name VARCHAR(100)
);

## Create Table with BIGINT

CREATE TABLE population_data (
    record_id INT PRIMARY KEY,
    population BIGINT
);