# SQL LIKE Commands

## Names Starting with A

SELECT *
FROM employees
WHERE name LIKE 'A%';

## Names Starting with R

SELECT *
FROM employees
WHERE name LIKE 'R%';

## Names Ending with a

SELECT *
FROM employees
WHERE name LIKE '%a';

## Names Containing it

SELECT *
FROM employees
WHERE name LIKE '%it%';

## Names with Second Character a

SELECT *
FROM employees
WHERE name LIKE '_a%';

## Names Not Starting with A

SELECT *
FROM employees
WHERE name NOT LIKE 'A%';