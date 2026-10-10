# SQL Data Types

SQL Data Types define what kind of data a column can store.

## 1. Numeric Data Types

### INT

Stores whole numbers.

Example:

age INT

### DECIMAL

Stores exact decimal values.

Example:

salary DECIMAL(10,2)

This allows up to 10 digits in total, with 2 digits after the decimal point.

### FLOAT

Stores approximate decimal values.

Example:

percentage FLOAT

### BIGINT

Stores large whole numbers.

Example:

population BIGINT

## 2. String Data Types

### CHAR

Stores fixed-length strings.

Example:

gender CHAR(1)

### VARCHAR

Stores variable-length strings up to a specified maximum.

Example:

name VARCHAR(100)

### TEXT

Stores longer text values.

Example:

description TEXT

## 3. Date and Time Data Types

### DATE

Stores a date.

Example:

birth_date DATE

Format: YYYY-MM-DD

### TIME

Stores a time.

Example:

start_time TIME

### DATETIME

Stores date and time.

Example:

created_at DATETIME

### TIMESTAMP

Stores date and time values, commonly used for recording when a row was created or updated.

Example:

updated_at TIMESTAMP

## 4. BOOLEAN

Represents TRUE or FALSE.

Example:

is_active BOOLEAN

In MySQL, BOOLEAN is treated as a synonym for TINYINT(1).

## Important

Choose a data type according to the data you need to store.

For money, DECIMAL is generally preferred over FLOAT because DECIMAL stores exact decimal value.