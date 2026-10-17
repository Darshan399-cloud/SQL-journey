# SQL JSON Functions - Commands

## 1. Create Table

CREATE TABLE employees (
    id INT PRIMARY KEY,
    details JSON
);

## 2. Insert JSON Data

INSERT INTO employees
VALUES (
    1,
    '{"name": "Rahul", "age": 22, "city": "Pune"}'
);

INSERT INTO employees
VALUES (
    2,
    '{"name": "Priya", "age": 24, "city": "Mumbai"}'
);

INSERT INTO employees
VALUES (
    3,
    '{"name": "Amit", "age": 25, "city": "Nashik"}'
);

## 3. Display All Data

SELECT * FROM employees;

## 4. Extract Employee Name

SELECT details->>'$.name' AS name
FROM employees;

## 5. Extract Employee Age

SELECT details->>'$.age' AS age
FROM employees;

## 6. Find Employees from Pune

SELECT *
FROM employees
WHERE details->>'$.city' = 'Pune';

## 7. Update City in JSON

UPDATE employees
SET details = JSON_SET(details, '$.city', 'Delhi')
WHERE id = 1;

## 8. Add a New Key

UPDATE employees
SET details = JSON_INSERT(details, '$.department', 'IT')
WHERE id = 2;

## 9. Remove a Key

UPDATE employees
SET details = JSON_REMOVE(details, '$.age')
WHERE id = 3;

## 10. Count JSON Elements

SELECT JSON_LENGTH(details)
FROM employees;

## 11. Display JSON Keys

SELECT JSON_KEYS(details)
FROM employees;