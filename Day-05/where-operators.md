# WHERE Operators

## Comparison Operators

=   Equal to

>   Greater than

<   Less than

>=  Greater than or equal to

<=  Less than or equal to

<>  Not equal to

## Logical Operators

### AND

SELECT *
FROM employees
WHERE department = 'IT' AND salary > 50000;

### OR

SELECT *
FROM employees
WHERE department = 'IT' OR department = 'HR';

### NOT

SELECT *
FROM employees
WHERE NOT department = 'HR';