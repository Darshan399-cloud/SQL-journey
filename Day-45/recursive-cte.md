# SQL Recursive CTE

A Recursive CTE is a CTE that refers to itself.

It is useful for hierarchical data such as:

- Employee and Manager
- Organization structures
- Categories and Subcategories
- Tree structures

## Basic Structure

WITH RECURSIVE cte_name AS (

    -- Anchor Query
    SELECT ...

    UNION ALL

    -- Recursive Query
    SELECT ...
    FROM cte_name
    WHERE condition
)

SELECT *
FROM cte_name;

## Number Example

WITH RECURSIVE numbers AS (

    SELECT 1 AS number

    UNION ALL

    SELECT number + 1
    FROM numbers
    WHERE number < 5
)

SELECT *
FROM numbers;

Result:

1
2
3
4
5

## Employee Hierarchy Example

employees

employee_id | name    | manager_id

101         | Darshan | NULL
102         | Rahul   | 101
103         | Amit    | 101
104         | Priya   | 102

The manager_id represents the manager of an employee.

A Recursive CTE can be used to process this hierarchy.

## Important

A Recursive CTE contains:

1. Anchor Query
2. UNION ALL
3. Recursive Query

The recursive query continues until the condition becomes false.