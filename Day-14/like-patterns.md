# LIKE Patterns

## Percentage (%) Wildcard

% represents zero or more characters.

Example:

SELECT *
FROM employees
WHERE name LIKE 'R%';

## Underscore (_) Wildcard

_ represents exactly one character.

Example:

SELECT *
FROM employees
WHERE name LIKE '_a%';

## Starts With

SELECT *
FROM employees
WHERE name LIKE 'Ra%';

## Ends With

SELECT *
FROM employees
WHERE name LIKE '%sh';

## Contains

SELECT *
FROM employees
WHERE name LIKE '%ah%';

## Single Character Pattern

SELECT *
FROM employees
WHERE name LIKE 'R_hul';