# SQL JSON Operations

Assume we have a table named employees with a JSON column called details.

## 1. Read a JSON Value

SELECT details->'$.name' AS employee_name
FROM employees;

## 2. Read a Value as Text

SELECT details->>'$.name' AS employee_name
FROM employees;

The ->> operator returns the extracted value as text.

## 3. JSON_SET()

It adds a key or updates an existing key.

Example:
SELECT JSON_SET(
    '{"name": "Rahul", "age": 22}',
    '$.age', 23
);

## 4. JSON_INSERT()

It inserts a value only if the specified path does not already exist.

Example:
SELECT JSON_INSERT(
    '{"name": "Rahul"}',
    '$.city', 'Pune'
);

## 5. JSON_REPLACE()

It updates a value only if the specified path already exists.

Example:
SELECT JSON_REPLACE(
    '{"name": "Rahul", "age": 22}',
    '$.age', 23
);

## 6. JSON_REMOVE()

It removes a key or array element.

Example:
SELECT JSON_REMOVE(
    '{"name": "Rahul", "age": 22}',
    '$.age'
);

## 7. Update JSON Data in a Table

UPDATE employees
SET details = JSON_SET(details, '$.city', 'Pune')
WHERE id = 1;

## 8. Important Difference

JSON_SET():
Adds a missing key or updates an existing key.

JSON_INSERT():
Adds a key only when it does not exist.

JSON_REPLACE():
Updates a key only when it already exists.

JSON_REMOVE():
Removes a key or array element.