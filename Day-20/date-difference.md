# SQL Date Difference

## DATEDIFF()

DATEDIFF() returns the difference between two dates in days.

SELECT DATEDIFF('2026-09-04', '2026-09-01');

## Difference Between Dates

SELECT DATEDIFF('2026-09-04', '2026-01-01');

## TIMESTAMPDIFF()

TIMESTAMPDIFF() calculates the difference between two dates using a specified unit.

## Difference in Days

SELECT TIMESTAMPDIFF(DAY, '2026-01-01', '2026-09-04');

## Difference in Months

SELECT TIMESTAMPDIFF(MONTH, '2026-01-01', '2026-09-04');

## Difference in Years

SELECT TIMESTAMPDIFF(YEAR, '2020-01-01', '2026-09-04');

## Employee Experience

SELECT name,
       TIMESTAMPDIFF(YEAR, joining_date, CURDATE()) AS experience_years
FROM employees;