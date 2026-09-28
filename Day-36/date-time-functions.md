# SQL Date and Time Functions

Date and Time Functions are used to work with date and time values.

## CURRENT_DATE()

Returns the current date.

Example:

SELECT CURRENT_DATE();

## CURRENT_TIME()

Returns the current time.

Example:

SELECT CURRENT_TIME();

## NOW()

Returns the current date and time.

Example:

SELECT NOW();

## DATE()

Extracts the date part from a date and time value.

Example:

SELECT DATE(NOW());

## YEAR()

Returns the year from a date.

Example:

SELECT YEAR('2026-09-28');

## MONTH()

Returns the month from a date.

Example:

SELECT MONTH('2026-09-28');

## DAY()

Returns the day from a date.

Example:

SELECT DAY('2026-09-28');

## DATE_FORMAT()

Formats a date according to the specified format.

Example:

SELECT DATE_FORMAT('2026-09-28', '%d-%m-%Y');