# Materialized Views

## 1. What is a Materialized View?

A Materialized View stores the result of an SQL query physically.

Unlike a normal view, it stores the query result.
It needs to be refreshed when the underlying data changes.

## 2. Example

Suppose we want to store total sales for each order.

A materialized view could store the result of:

SELECT
    order_id,
    SUM(quantity * unit_price) AS total_amount
FROM order_items
GROUP BY order_id;

## 3. Advantages

1. Faster data retrieval for repeated complex queries.
2. Stores precomputed results.
3. Useful for reporting and analytics.
4. Reduces repeated calculations.

## 4. Disadvantages

1. Requires additional storage.
2. Data may become outdated.
3. Refreshing requires additional work.
4. Maintenance can be complex.

## 5. Materialized Views in MySQL

MySQL does not provide native CREATE MATERIALIZED VIEW syntax.

A similar result can be achieved using a table.

Example:

CREATE TABLE order_sales_summary AS
SELECT
    order_id,
    SUM(quantity * unit_price) AS total_amount
FROM order_items
GROUP BY order_id;

To refresh the stored result:

TRUNCATE TABLE order_sales_summary;

INSERT INTO order_sales_summary
SELECT
    order_id,
    SUM(quantity * unit_price)
FROM order_items
GROUP BY order_id;

Note:
This is a manually maintained summary table, not a native materialized view.