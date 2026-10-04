# SQL Cursors

A Cursor is used to process query results one row at a time.

Normally, SQL works with multiple rows at once.

A Cursor allows us to process each row individually.

## Cursor Steps

1. DECLARE Cursor
2. OPEN Cursor
3. FETCH Data
4. Process Data
5. CLOSE Cursor

## Basic Syntax

DECLARE cursor_name CURSOR FOR
SELECT column_name
FROM table_name;

## Example

DECLARE employee_cursor CURSOR FOR
SELECT name
FROM employees;

## Important

A Cursor is normally used inside a Stored Procedure or another stored program.

Cursors are useful when row-by-row processing is required.

## Advantages

- Processes records one by one
- Useful for complex row-level logic
- Can be used with Stored Procedures

## Disadvantages

- Usually slower than normal SQL queries
- Can consume more resources
- Should not be used when a normal SQL query can solve the problem