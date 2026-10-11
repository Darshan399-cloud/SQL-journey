# SQL Temporary Table Commands

## Create Employees Table

```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    salary DECIMAL(10,2)
);
```

## Insert Employees

```sql
INSERT INTO employees VALUES
(101, 'Darshan', 'IT', 50000),
(102, 'Rahul', 'IT', 65000),
(103, 'Amit', 'HR', 45000),
(104, 'Priya', 'Finance', 70000),
(105, 'Sneha', 'HR', 55000);
```

## Create Temporary Table

```sql
CREATE TEMPORARY TABLE temp_employees (
    employee_id INT,
    name VARCHAR(100),
    salary DECIMAL(10,2)
);
```

## Insert Records

```sql
INSERT INTO temp_employees VALUES
(101, 'Darshan', 50000),
(102, 'Rahul', 65000),
(103, 'Amit', 45000);
```

## Display Records

```sql
SELECT *
FROM temp_employees;
```

## Update Salary

```sql
UPDATE temp_employees
SET salary = 60000
WHERE employee_id = 101;
```

## Delete a Record

```sql
DELETE FROM temp_employees
WHERE employee_id = 103;
```

## Create Temporary Table Using SELECT

```sql
CREATE TEMPORARY TABLE high_salary_employees AS
SELECT employee_id, name, salary
FROM employees
WHERE salary >= 60000;
```

## Display High-Salary Employees

```sql
SELECT *
FROM high_salary_employees;
```

## Add a Column

```sql
ALTER TABLE temp_employees
ADD department VARCHAR(100);
```

## Display Table Structure

```sql
DESC temp_employees;
```

## Drop Temporary Tables

```sql
DROP TEMPORARY TABLE IF EXISTS temp_employees;

DROP TEMPORARY TABLE IF EXISTS high_salary_employees;
```