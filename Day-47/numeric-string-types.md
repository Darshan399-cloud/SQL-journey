# Numeric and String Data Types

## INT vs BIGINT

INT stores whole numbers within a smaller range.

BIGINT supports a much larger range of whole numbers.

## CHAR vs VARCHAR

CHAR stores fixed-length strings.

VARCHAR stores variable-length strings.

Example:

country_code CHAR(2)

name VARCHAR(100)

## DECIMAL vs FLOAT

DECIMAL stores exact decimal values.

FLOAT stores approximate decimal values.

Example:

price DECIMAL(10,2)

measurement FLOAT

## TEXT vs VARCHAR

VARCHAR is commonly used for names, emails and short text.

TEXT is useful for longer descriptions and content.

## DATE vs DATETIME

DATE stores only the date.

DATETIME stores both the date and time.

## DATETIME vs TIMESTAMP

DATETIME stores a date and time value.

TIMESTAMP is commonly used for recording events and may convert values according to the session time zone.

## Examples

CREATE TABLE students (
    student_id INT,
    name VARCHAR(100),
    age INT,
    percentage DECIMAL(5,2),
    birth_date DATE,
    is_active BOOLEAN
);

CREATE TABLE products (
    product_id INT,
    product_name VARCHAR(150),
    price DECIMAL(10,2),
    description TEXT,
    created_at DATETIME
);

## Important

The correct data type helps maintain data accuracy and use storage efficiently.