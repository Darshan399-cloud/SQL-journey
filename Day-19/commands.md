# SQL Date and Time Commands

## Current Date

SELECT CURDATE();

## Current Time

SELECT CURTIME();

## Current Date and Time

SELECT NOW();

## Current Timestamp

SELECT CURRENT_TIMESTAMP();

## Extract Date

SELECT DATE(NOW());

## Extract Year

SELECT YEAR('2026-09-02');

## Extract Month

SELECT MONTH('2026-09-02');

## Extract Day

SELECT DAY('2026-09-02');

## Extract Year from Column

SELECT name, YEAR(joining_date)
FROM employees;

## Extract Month from Column

SELECT name, MONTH(joining_date)
FROM employees;