# SQL Date Formatting and Difference Commands

## Format Date

SELECT DATE_FORMAT('2026-09-04', '%d-%m-%Y');

## Format Current Date

SELECT DATE_FORMAT(CURDATE(), '%d-%m-%Y');

## Format Joining Date

SELECT name, DATE_FORMAT(joining_date, '%d-%m-%Y')
FROM employees;

## Difference in Days

SELECT DATEDIFF('2026-09-04', '2026-09-01');

## Difference in Months

SELECT TIMESTAMPDIFF(MONTH, '2026-01-01', '2026-09-04');

## Difference in Years

SELECT TIMESTAMPDIFF(YEAR, '2020-01-01', '2026-09-04');

## Employee Experience

SELECT name,
       TIMESTAMPDIFF(YEAR, joining_date, CURDATE()) AS experience_years
FROM employees;