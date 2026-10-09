# SQL Ranking Functions

Ranking Functions assign a position to each row based on a specified order.

## ROW_NUMBER()

Assigns a unique sequential number to each row.

```sql
SELECT
    name,
    salary,
    ROW_NUMBER() OVER (
        ORDER BY salary DESC
    ) AS row_num
FROM employees;
```

## RANK()

Assigns the same rank to tied values and skips subsequent ranks.

```sql
SELECT
    name,
    salary,
    RANK() OVER (
        ORDER BY salary DESC
    ) AS salary_rank
FROM employees;
```

Example ranks when salaries tie:

1, 2, 2, 4

## DENSE_RANK()

Assigns the same rank to tied values without skipping the next rank.

```sql
SELECT
    name,
    salary,
    DENSE_RANK() OVER (
        ORDER BY salary DESC
    ) AS dense_salary_rank
FROM employees;
```

Example ranks when salaries tie:

1, 2, 2, 3

## Department-wise Ranking

```sql
SELECT
    name,
    department,
    salary,
    RANK() OVER (
        PARTITION BY department
        ORDER BY salary DESC
    ) AS department_rank
FROM employees;
```

This ranks employees by salary separately within each department.

## Difference

* ROW_NUMBER(): Every row gets a different number.
* RANK(): Tied values share a rank, and later ranks can be skipped.
* DENSE_RANK(): Tied values share a rank, with no gaps.
