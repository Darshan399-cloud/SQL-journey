# SQL Indexes

An Index is a database object used to make data retrieval faster.

Indexes are useful when a table contains a large amount of data.

## Why Use Indexes?

Without an Index, the database may need to check many rows to find matching data.

An Index can help the database find data more efficiently.

## Basic Syntax

CREATE INDEX index_name
ON table_name (column_name);

## Example

CREATE INDEX idx_employee_name
ON employees (name);

Now queries that search using the name column can use the index.

## UNIQUE Index

A UNIQUE Index prevents duplicate values in the indexed column.

Example:

CREATE UNIQUE INDEX idx_employee_email
ON employees (email);

## Composite Index

An Index can be created using multiple columns.

Example:

CREATE INDEX idx_employee_dept_salary
ON employees (department, salary);

## DROP INDEX

An Index can be removed when it is no longer required.

Syntax depends on the database system.

MySQL:

DROP INDEX index_name
ON table_name;

## Advantages

- Faster data retrieval
- Useful for large tables
- Can improve search performance
- Useful for columns frequently used in WHERE and JOIN conditions

## Disadvantages

- Requires additional storage
- INSERT operations can become slower
- UPDATE operations can become slower
- DELETE operations can require index maintenance

## Important

Indexes should be used carefully.

Creating an Index on every column is not always a good idea.