# SQL String Functions

String functions are used to manipulate and work with text values.

## UPPER()

UPPER() converts text into uppercase.

SELECT UPPER(name)
FROM employees;

## LOWER()

LOWER() converts text into lowercase.

SELECT LOWER(name)
FROM employees;

## LENGTH()

LENGTH() returns the number of characters in a string.

SELECT LENGTH(name)
FROM employees;

## CONCAT()

CONCAT() combines two or more strings.

SELECT CONCAT(name, ' - ', department)
FROM employees;

## SUBSTRING()

SUBSTRING() extracts a part of a string.

SELECT SUBSTRING(name, 1, 3)
FROM employees;

## TRIM()

TRIM() removes leading and trailing spaces.

SELECT TRIM(name)
FROM employees;