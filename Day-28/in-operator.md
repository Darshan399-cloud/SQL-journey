# SQL IN with Subquery

IN is used when a subquery can return multiple values.

## Syntax

SELECT column_name
FROM table_name
WHERE column_name IN (
    SELECT column_name
    FROM table_name
    WHERE condition
);

## Example

SELECT name, department
FROM employees
WHERE department IN (
    SELECT department_name
    FROM departments
    WHERE location = 'Pune'
);

The inner query can return multiple department names.

IN checks whether the employee's department exists in the returned list.

## NOT IN

NOT IN returns records whose value is not present in the subquery result.

Example:

SELECT name, department
FROM employees
WHERE department NOT IN (
    SELECT department_name
    FROM departments
    WHERE location = 'Pune'
);