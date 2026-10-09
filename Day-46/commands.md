# SQL Window Function Commands

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
(105, 'Sneha', 'HR', 55000),
(106, 'Kiran', 'IT', 65000);
```

## Display All Employees

```sql
SELECT * FROM employees;
```

## ROW_NUMBER()

```sql
SELECT
    name,
    salary,
    ROW_NUMBER() OVER (
        ORDER BY salary DESC, employee_id
    ) AS row_num
FROM employees;
```

## RANK()

```sql
SELECT
    name,
    salary,
    RANK() OVER (
        ORDER BY salary DESC
    ) AS salary_rank
FROM employees;
```

## DENSE_RANK()

```sql
SELECT
    name,
    salary,
    DENSE_RANK() OVER (
        ORDER BY salary DESC
    ) AS dense_rank
FROM employees;
```

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

## Department Average

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

## Running Total

```sql
SELECT
    employee_id,
    name,
    salary,
    SUM(salary) OVER (
        ORDER BY employee_id
        ROWS BETWEEN UNBOUNDED PRECEDING
        AND CURRENT ROW
    ) AS running_total
FROM employees;
```

## Previous Salary

```sql
SELECT
    name,
    salary,
    LAG(salary) OVER (
        ORDER BY employee_id
    ) AS previous_salary
FROM employees;
```

## Next Salary

```sql
SELECT
    name,
    salary,
    LEAD(salary) OVER (
        ORDER BY employee_id
    ) AS next_salary
FROM employees;
```
