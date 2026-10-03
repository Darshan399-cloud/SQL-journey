# SQL Built-in Functions

Built-in Functions are functions already provided by the database system.

They can be used without creating our own function.

## String Functions

### UPPER()

Converts text to uppercase.

SELECT UPPER('darshan');

### LOWER()

Converts text to lowercase.

SELECT LOWER('DARSHAN');

### LENGTH()

Returns the length of a string.

SELECT LENGTH('Darshan');

## Numeric Functions

### ROUND()

Rounds a number.

SELECT ROUND(125.678, 2);

### CEIL()

Returns the smallest integer greater than or equal to a number.

SELECT CEIL(125.2);

### FLOOR()

Returns the largest integer less than or equal to a number.

SELECT FLOOR(125.8);

## Date Functions

### CURRENT_DATE()

Returns the current date.

SELECT CURRENT_DATE();

### NOW()

Returns the current date and time.

SELECT NOW();

## Aggregate Functions

### COUNT()

SELECT COUNT(*)
FROM employees;

### SUM()

SELECT SUM(salary)
FROM employees;

### AVG()

SELECT AVG(salary)
FROM employees;

## Important

Built-in Functions are already available in SQL.

User-Defined Functions are created by the developer according to the requirement.