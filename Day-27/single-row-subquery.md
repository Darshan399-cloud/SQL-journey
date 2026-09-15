# Single-Row Subquery

A single-row subquery returns only one value or one row.

It is commonly used with comparison operators such as:

- =
- >
- <
- >=
- <=
- <>

## Example

SELECT name, salary
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);

The AVG() function returns one value, so it can be used with the > operator.

## Highest Salary

SELECT name, salary
FROM employees
WHERE salary = (
    SELECT MAX(salary)
    FROM employees
);

## Lowest Salary

SELECT name, salary
FROM employees
WHERE salary = (
    SELECT MIN(salary)
    FROM employees
);

## Important

If a subquery returns multiple rows, using = may produce an error.

For multiple-row results, operators such as IN can be used.