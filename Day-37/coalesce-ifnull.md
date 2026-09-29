# IFNULL() and COALESCE()

## IFNULL()

IFNULL() checks one value.

If the value is NULL, it returns the replacement value.

Example:

SELECT
    name,
    IFNULL(email, 'No Email') AS email
FROM employees;

## COALESCE()

COALESCE() can check multiple values.

It returns the first non-NULL value.

Example:

SELECT
    name,
    COALESCE(phone, email, 'No Contact') AS contact
FROM employees;

## Difference

IFNULL()

- Checks one value
- Uses one replacement value
- Commonly used in MySQL

COALESCE()

- Can check multiple values
- Returns the first non-NULL value
- Standard SQL function

## Example

phone = NULL
email = 'darshan@example.com'

COALESCE(phone, email, 'No Contact')

Result:

darshan@example.com