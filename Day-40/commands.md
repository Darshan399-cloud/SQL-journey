# SQL Function Commands

## Create Employees Table

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    salary DECIMAL(10,2)
);

## Insert Employees

INSERT INTO employees
VALUES (101, 'Darshan', 'IT', 50000);

INSERT INTO employees
VALUES (102, 'Rahul', 'IT', 65000);

INSERT INTO employees
VALUES (103, 'Amit', 'HR', 45000);

INSERT INTO employees
VALUES (104, 'Priya', 'Finance', 70000);

## Create Addition Function

DELIMITER //

CREATE FUNCTION add_numbers(
    a INT,
    b INT
)
RETURNS INT
DETERMINISTIC
BEGIN
    RETURN a + b;
END //

DELIMITER ;

## Call Addition Function

SELECT add_numbers(10, 20);

## Create Annual Salary Function

DELIMITER //

CREATE FUNCTION annual_salary(
    monthly_salary DECIMAL(10,2)
)
RETURNS DECIMAL(10,2)
DETERMINISTIC
BEGIN
    RETURN monthly_salary * 12;
END //

DELIMITER ;

## Call Annual Salary Function

SELECT annual_salary(50000);

## Use Function with Employees

SELECT
    name,
    salary,
    annual_salary(salary) AS yearly_salary
FROM employees;

## Built-in String Function

SELECT
    name,
    UPPER(name) AS uppercase_name
FROM employees;

## Built-in Numeric Function

SELECT
    salary,
    ROUND(salary / 12, 2) AS monthly_value
FROM employees;

## Built-in Aggregate Function

SELECT
    COUNT(*) AS total_employees,
    SUM(salary) AS total_salary,
    AVG(salary) AS average_salary
FROM employees;

## Show Functions

SHOW FUNCTION STATUS
WHERE Db = DATABASE();

## Drop Function

DROP FUNCTION add_numbers;

DROP FUNCTION annual_salary;