# SQL Temporary Tables

A Temporary Table is a table used to store data temporarily during a database session.

In MySQL, a Temporary Table is available only to the session that created it and is automatically removed when that session ends.

## Basic Syntax

```sql
CREATE TEMPORARY TABLE table_name (
    column1 datatype,
    column2 datatype
);
```

## Create a Temporary Table

```sql
CREATE TEMPORARY TABLE temp_employees (
    employee_id INT,
    name VARCHAR(100),
    salary DECIMAL(10,2)
);
```

## Insert Records

```sql
INSERT INTO temp_employees
VALUES (101, 'Darshan', 50000);

INSERT INTO temp_employees
VALUES (102, 'Rahul', 60000);
```

## Display Records

```sql
SELECT *
FROM temp_employees;
```

## Create Temporary Table Using SELECT

```sql
CREATE TEMPORARY TABLE high_salary_employees AS
SELECT employee_id, name, salary
FROM employees
WHERE salary >= 60000;
```

This creates a Temporary Table containing employees earning at least 60000.

## Important Features

- Temporary Tables store data temporarily.
- They are available only in the session that created them.
- They can be used for intermediate query results.
- MySQL automatically removes them when the session ends.
- A Temporary Table can have indexes.
- Other sessions cannot access your Temporary Table.