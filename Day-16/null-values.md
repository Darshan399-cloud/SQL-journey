# NULL Values

NULL represents a missing, unknown or unavailable value.

NULL is different from zero.

NULL is also different from an empty string.

## NULL Example

| id | name  | department | salary |
|----|-------|------------|--------|
| 1  | Rahul | IT         | 50000  |
| 2  | Amit  | NULL       | 45000  |

The department of Amit is NULL.

## IS NULL

IS NULL is used to find records containing NULL values.

SELECT *
FROM employees
WHERE department IS NULL;

## IS NOT NULL

IS NOT NULL is used to find records that do not contain NULL values.

SELECT *
FROM employees
WHERE department IS NOT NULL;