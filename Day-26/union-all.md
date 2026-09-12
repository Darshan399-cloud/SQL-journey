# SQL UNION ALL

UNION ALL combines the result of two or more SELECT statements.

Unlike UNION, UNION ALL keeps duplicate records.

## Syntax

SELECT column1
FROM table1

UNION ALL

SELECT column1
FROM table2;

## Example

SELECT name
FROM employees

UNION ALL

SELECT name
FROM managers;

## UNION vs UNION ALL

UNION
- Combines results
- Removes duplicates
- May require additional processing

UNION ALL
- Combines results
- Keeps duplicates
- Generally faster than UNION