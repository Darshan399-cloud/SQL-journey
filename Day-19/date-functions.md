# SQL Date and Time Functions

Date and time functions are used to work with date and time values.

## CURDATE()

CURDATE() returns the current date.

SELECT CURDATE();

## CURRENT_DATE()

CURRENT_DATE() returns the current date.

SELECT CURRENT_DATE();

## NOW()

NOW() returns the current date and time.

SELECT NOW();

## CURRENT_TIMESTAMP()

CURRENT_TIMESTAMP() returns the current date and time.

SELECT CURRENT_TIMESTAMP();

## CURTIME()

CURTIME() returns the current time.

SELECT CURTIME();

## DATE()

DATE() extracts the date part from a datetime value.

SELECT DATE(NOW());

## YEAR()

YEAR() returns the year from a date.

SELECT YEAR('2026-09-02');

## MONTH()

MONTH() returns the month from a date.

SELECT MONTH('2026-09-02');

## DAY()

DAY() returns the day from a date.

SELECT DAY('2026-09-02');