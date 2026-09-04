# SQL Date Formatting

## DATE_FORMAT()

DATE_FORMAT() is used to display a date in a specific format.

SELECT DATE_FORMAT('2026-09-04', '%d-%m-%Y');

## Day-Month-Year

SELECT DATE_FORMAT('2026-09-04', '%d-%m-%Y');

## Month-Day-Year

SELECT DATE_FORMAT('2026-09-04', '%m-%d-%Y');

## Year-Month-Day

SELECT DATE_FORMAT('2026-09-04', '%Y-%m-%d');

## Month Name

SELECT DATE_FORMAT('2026-09-04', '%M');

## Day Name

SELECT DATE_FORMAT('2026-09-04', '%W');

## Format Date Column

SELECT name, DATE_FORMAT(joining_date, '%d-%m-%Y') AS joining_date
FROM employees;