# UPDATE Conditions

## UPDATE with WHERE

UPDATE employees
SET salary = 70000
WHERE department = 'IT';

## Update Specific Employee

UPDATE employees
SET salary = 55000
WHERE name = 'Rahul';

## Update Multiple Records

UPDATE employees
SET department = 'HR'
WHERE salary < 40000;

## UPDATE without WHERE

UPDATE employees
SET department = 'IT';

This updates the department for all records in the table.