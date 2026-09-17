# CASE with Aggregate Functions

CASE can be used together with aggregate functions.

It is commonly used to count or calculate records based on conditions.

## COUNT with CASE

SELECT
    COUNT(
        CASE
            WHEN salary >= 60000 THEN 1
        END
    ) AS high_salary_employees
FROM employees;

## SUM with CASE

SELECT
    SUM(
        CASE
            WHEN salary >= 60000 THEN salary
            ELSE 0
        END
    ) AS high_salary_total
FROM employees;

## CASE with AVG

SELECT
    AVG(
        CASE
            WHEN department = 'IT' THEN salary
        END
    ) AS average_it_salary
FROM employees;

## CASE with GROUP BY

SELECT
    department,
    CASE
        WHEN AVG(salary) >= 60000 THEN 'High Average'
        ELSE 'Normal Average'
    END AS salary_level
FROM employees
GROUP BY department;