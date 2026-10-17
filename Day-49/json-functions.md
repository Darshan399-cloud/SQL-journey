# SQL JSON Functions

## 1. What is JSON?

JSON stands for JavaScript Object Notation.
It stores data in key-value pairs and arrays.

Example:
{
  "name": "Rahul",
  "age": 22,
  "city": "Pune"
}

## 2. JSON Data Type

MySQL provides a JSON data type to store JSON documents.

Syntax:
CREATE TABLE students (
    id INT PRIMARY KEY,
    details JSON
);

## 3. JSON_OBJECT()

It creates a JSON object using key-value pairs.

Example:
SELECT JSON_OBJECT(
    'name', 'Rahul',
    'age', 22
);

## 4. JSON_ARRAY()

It creates a JSON array.

Example:
SELECT JSON_ARRAY('Java', 'SQL', 'Python');

## 5. JSON_EXTRACT()

It extracts a value from JSON data.

Example:
SELECT JSON_EXTRACT(
    '{"name": "Rahul", "age": 22}',
    '$.name'
);

Output:
"Rahul"

## 6. JSON_KEYS()

It returns the keys of a JSON object.

Example:
SELECT JSON_KEYS(
    '{"name": "Rahul", "age": 22}'
);

## 7. JSON_LENGTH()

It returns the number of elements in a JSON object or array.

Example:
SELECT JSON_LENGTH('[10, 20, 30]');

Output:
3

## 8. JSON_CONTAINS()

It checks whether a JSON document contains a given value.

Example:
SELECT JSON_CONTAINS(
    '[10, 20, 30]',
    '20'
);

Output:
1

Here, 1 means true and 0 means false.

Note:
These examples use MySQL JSON function syntax.