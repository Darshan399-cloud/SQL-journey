# SQL Window Functions

Window Functions perform calculations across related rows without combining them into a single row.

## Basic Syntax

```sql
function_name() OVER (
    PARTITION BY column_name
    ORDER BY column_name
)
```

## OVER()

OVER() defines the rows used by a Window Function.

```sql
SELECT
    name,
    salary,
    SUM(salary) OVER () AS total_salary
FROM employees;
```

This displays each employee along with the total salary of all employees.

## PARTITION BY

PARTITION BY divides rows into groups for calculation.

```sql
SELECT
    name,
    department,
    salary,
    AVG(salary) OVER (
        PARTITION BY department
    ) AS department_average
FROM employees;
```

This displays each employee's salary and their department's average salary.

## Running Total

```sql
SELECT
    name,
    salary,
    SUM(salary) OVER (
        ORDER BY employee_id
        ROWS BETWEEN UNBOUNDED PRECEDING
        AND CURRENT ROW
    ) AS running_total
FROM employees;
```

This calculates a cumulative salary total in employee ID order.

## LAG()

LAG() returns a value from a previous row.

```sql
SELECT
    name,
    salary,
    LAG(salary) OVER (
        ORDER BY employee_id
    ) AS previous_salary
FROM employees;
```

## LEAD()

LEAD() returns a value from a following row.

```sql
SELECT
    name,
    salary,
    LEAD(salary) OVER (
        ORDER BY employee_id
    ) AS next_salary
FROM employees;
```

## Important

Window Functions preserve individual rows.

Unlike GROUP BY, they do not combine all rows in each group into one result row.
