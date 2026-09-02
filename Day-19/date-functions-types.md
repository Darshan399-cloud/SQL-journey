# Date Function Examples

## Current Date

SELECT CURDATE() AS current_date;

## Current Time

SELECT CURTIME() AS current_time;

## Current Date and Time

SELECT NOW() AS current_datetime;

## Extract Date

SELECT DATE(NOW()) AS current_date;

## Extract Year

SELECT YEAR('2026-09-02') AS year_value;

## Extract Month

SELECT MONTH('2026-09-02') AS month_value;

## Extract Day

SELECT DAY('2026-09-02') AS day_value;

## Date Column

SELECT name, joining_date
FROM employees;

## Extract Year from Column

SELECT name, YEAR(joining_date) AS joining_year
FROM employees;

## Extract Month from Column

SELECT name, MONTH(joining_date) AS joining_month
FROM employees;