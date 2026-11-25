# SQL Views

## 1. What is a View?

A View is a virtual table created using an SQL query.
It displays data from one or more existing tables.

A View usually does not store the actual data.
It stores the SQL query used to retrieve the data.

## 2. Syntax

CREATE VIEW view_name AS
SELECT column1, column2
FROM table_name;

## 3. Create a View

CREATE VIEW customer_view AS
SELECT customer_id, customer_name, city
FROM customers;

## 4. Retrieve Data from a View

SELECT * FROM customer_view;

## 5. Create a View Using Multiple Tables

CREATE VIEW order_details_view AS
SELECT
    o.order_id,
    c.customer_name,
    o.order_date,
    o.status
FROM orders o
JOIN customers c
ON o.customer_id = c.customer_id;

## 6. Update a View

Some simple views are updatable.

Example:

UPDATE customer_view
SET city = 'Pune'
WHERE customer_id = 1;

Note:
A view containing joins, grouping, or aggregate functions may not be updatable.

## 7. Drop a View

DROP VIEW customer_view;

## 8. Advantages of Views

1. Simplifies complex SQL queries.
2. Improves data security.
3. Hides unnecessary columns.
4. Provides customized data.
5. Helps organize database queries.
6. Reduces repeated query writing.
7. Makes data access easier.

## 9. Disadvantages of Views

1. Complex views may be slow.
2. Some views cannot be updated.
3. Views depend on underlying tables.
4. Changes in table structure can affect views.