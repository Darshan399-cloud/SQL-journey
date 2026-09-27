# SQL String Functions

String functions are used to manipulate and process text values.

## CONCAT()

CONCAT() combines two or more strings.

Example:

SELECT CONCAT(first_name, ' ', last_name)
FROM employees;

## UPPER()

UPPER() converts text to uppercase.

Example:

SELECT UPPER(name)
FROM employees;

## LOWER()

LOWER() converts text to lowercase.

Example:

SELECT LOWER(name)
FROM employees;

## LENGTH()

LENGTH() returns the number of characters in a string.

Example:

SELECT LENGTH(name)
FROM employees;

## TRIM()

TRIM() removes spaces from the beginning and end of a string.

Example:

SELECT TRIM(name)
FROM employees;

## SUBSTRING()

SUBSTRING() extracts a part of a string.

Example:

SELECT SUBSTRING(name, 1, 3)
FROM employees;

## REPLACE()

REPLACE() replaces part of a string with another string.

Example:

SELECT REPLACE(name, 'a', 'A')
FROM employees;