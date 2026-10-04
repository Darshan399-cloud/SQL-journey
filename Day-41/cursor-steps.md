# SQL Cursor Steps

## Step 1 - Declare Variables

DECLARE employee_name VARCHAR(100);
DECLARE finished INT DEFAULT 0;

## Step 2 - Declare Cursor

DECLARE employee_cursor CURSOR FOR
SELECT name
FROM employees;

## Step 3 - Declare Handler

DECLARE CONTINUE HANDLER
FOR NOT FOUND SET finished = 1;

The handler detects when there are no more rows to fetch.

## Step 4 - Open Cursor

OPEN employee_cursor;

## Step 5 - Fetch Data

FETCH employee_cursor
INTO employee_name;

The FETCH statement gets the next row from the Cursor.

## Step 6 - Process Data

The fetched value can be used inside SQL statements.

Example:

SELECT employee_name;

## Step 7 - Close Cursor

CLOSE employee_cursor;

## Complete Flow

DECLARE
     
OPEN
     
FETCH
     
PROCESS
     
FETCH
     
PROCESS
     
CLOSE

## Important

Cursors should be used carefully because row-by-row processing can be slower than set-based SQL queries.