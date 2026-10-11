# Temporary Table Operations

## SELECT

Retrieves records from a Temporary Table.

```sql
SELECT *
FROM temp_employees;
```

## UPDATE

Changes existing records.

```sql
UPDATE temp_employees
SET salary = 65000
WHERE employee_id = 101;
```

## DELETE

Removes records from a Temporary Table.

```sql
DELETE FROM temp_employees
WHERE employee_id = 102;
```

## ALTER TABLE

Adds a new column.

```sql
ALTER TABLE temp_employees
ADD department VARCHAR(100);
```

## Create an Index

```sql
CREATE INDEX idx_temp_employee_name
ON temp_employees(name);
```

## DROP TEMPORARY TABLE

Removes a Temporary Table before the session ends.

```sql
DROP TEMPORARY TABLE temp_employees;
```

## Temporary Table vs Regular Table

| Temporary Table | Regular Table |
|---|---|
| Used for temporary data | Used for persistent data |
| Available only in its creating session in MySQL | Can be accessed by authorized sessions |
| Automatically removed when the session ends | Remains until explicitly dropped |
| Useful for intermediate results | Useful for permanent application data |

## Important

In MySQL, `CREATE TEMPORARY TABLE` creates a session-specific table. A Temporary Table can have the same name as a regular table in the same database, and the temporary table hides the regular table for that session while it exists.