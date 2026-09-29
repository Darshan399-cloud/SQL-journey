# SQL NULL Functions

NULL represents a missing or unknown value.

NULL is different from 0, an empty string, or a space.

## IS NULL

IS NULL is used to find records containing NULL.

Example:

SELECT *
FROM employees
WHERE manager_id IS NULL;

## IS NOT NULL

IS NOT NULL is used to find records that do not contain NULL.

Example:

SELECT *
FROM employees
WHERE manager_id IS NOT NULL;

## Important

Do not use = NULL to check for NULL values.

Incorrect:

WHERE manager_id = NULL;

Correct:

WHERE manager_id IS NULL;

## IFNULL()

IFNULL() replaces a NULL value with another value.

Syntax:

IFNULL(value, replacement_value)

Example:

SELECT
    name,
    IFNULL(phone, 'Not Available') AS phone
FROM employees;

## COALESCE()

COALESCE() returns the first non-NULL value from a list.

Example:

SELECT
    name,
    COALESCE(phone, email, 'No Contact') AS contact
FROM employees;

## NULLIF()

NULLIF() returns NULL when two expressions are equal.

Example:

SELECT NULLIF(10, 10);

Result:

NULL

Example:

SELECT NULLIF(10, 20);

Result:

10