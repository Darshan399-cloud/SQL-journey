
# Types of INSERT

## Insert Single Row

INSERT INTO employees
VALUES (1, 'Rahul', 'IT', 50000);

## Insert Multiple Rows

INSERT INTO employees
VALUES
(2, 'Amit', 'HR', 45000),
(3, 'Priya', 'Finance', 55000);

## Insert into Specific Columns

INSERT INTO employees (id, name, department)
VALUES (4, 'Rohit', 'IT');

## Insert with Different Column Order

INSERT INTO employees (name, department, salary, id)
VALUES ('Neha', 'Finance', 60000, 5);