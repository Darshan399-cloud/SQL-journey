# SQL EXISTS and NOT EXISTS

## EXISTS

EXISTS checks whether a subquery returns at least one record.

It returns TRUE when a matching record exists.

## Syntax

SELECT column_name
FROM table1
WHERE EXISTS (
    SELECT 1
    FROM table2
    WHERE table1.column = table2.column
);

## Example

SELECT name
FROM employees e
WHERE EXISTS (
    SELECT 1
    FROM departments d
    WHERE e.department_id = d.department_id
);

This returns employees whose department exists.

## NOT EXISTS

NOT EXISTS checks whether no matching record exists.

## Example

SELECT name
FROM employees e
WHERE NOT EXISTS (
    SELECT 1
    FROM departments d
    WHERE e.department_id = d.department_id
);

This returns employees whose department does not have a matching record.

## Important

EXISTS checks whether at least one matching row exists.

NOT EXISTS checks whether no matching row exists.