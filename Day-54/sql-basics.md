# SQL Mock Interview - Basic Questions

## 1. What is SQL?

SQL stands for Structured Query Language.
It is used to store, retrieve, update, and delete data in relational databases.

## 2. What is a Database?

A database is an organized collection of data.

## 3. What is a Table?

A table stores data in rows and columns.

## 4. What is a Primary Key?

A primary key uniquely identifies each row in a table.
It cannot contain duplicate or NULL values.

## 5. What is a Foreign Key?

A foreign key creates a relationship between tables by referring to a key in another table.

## 6. What is the Difference Between DELETE, DROP, and TRUNCATE?

DELETE:
Removes selected rows or all rows from a table.

DROP:
Removes the table structure and its data.

TRUNCATE:
Removes all rows while keeping the table structure.

## 7. What is the Difference Between WHERE and HAVING?

WHERE filters individual rows before grouping.

HAVING filters groups after GROUP BY.

## 8. What is NULL?

NULL represents a missing or unknown value.

Use IS NULL to check for NULL values.

## 9. What are Aggregate Functions?

Aggregate functions calculate results from multiple rows.

Examples:
COUNT(), SUM(), AVG(), MIN(), MAX()

## 10. What is GROUP BY?

GROUP BY combines rows with the same values into groups.

Example:

SELECT department_id, COUNT(*)
FROM employees
GROUP BY department_id;

## 11. What is ORDER BY?

ORDER BY sorts query results in ascending or descending order.

## 12. What is DISTINCT?

DISTINCT removes duplicate rows from the query result.

## 13. What is a JOIN?

A JOIN combines related data from two or more tables.

## 14. What is a Subquery?

A subquery is a query written inside another SQL query.

## 15. What is an Index?

An index helps the database find data faster, but it can require extra storage and slow down some write operations.