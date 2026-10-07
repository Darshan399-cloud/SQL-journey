# SQL EXPLAIN

EXPLAIN is used to understand how MySQL executes a SELECT query.

It helps identify:

- Which table is being accessed
- Which indexes are used
- How many rows may be examined
- How tables are joined

## Basic Syntax

EXPLAIN
SELECT *
FROM employees;

## EXPLAIN with WHERE

EXPLAIN
SELECT name, salary
FROM employees
WHERE department = 'IT';

## EXPLAIN with JOIN

EXPLAIN
SELECT
    e.name,
    d.department_name
FROM employees e
INNER JOIN departments d
ON e.department_id = d.department_id;

## Common EXPLAIN Columns

### id

Identifies the SELECT operation.

### table

Shows the table being accessed.

### type

Shows the type of table access.

### possible_keys

Shows indexes that could be used.

### key

Shows the index actually used.

### rows

Shows the estimated number of rows examined.

### Extra

Provides additional information about query execution.

## Important

EXPLAIN does not change the data.

It is mainly used to analyze query execution.