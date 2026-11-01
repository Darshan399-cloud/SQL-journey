-- Create Database
CREATE DATABASE ecommerce_db;

-- Select Database
USE ecommerce_db;

-- 1. Create Customers Table
CREATE TABLE customers (
    customer_id INT PRIMARY KEY AUTO_INCREMENT,
    customer_name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    city VARCHAR(50)
);

-- 2. Create Categories Table
CREATE TABLE categories (
    category_id INT PRIMARY KEY AUTO_INCREMENT,
    category_name VARCHAR(100) NOT NULL
);

-- 3. Create Products Table
CREATE TABLE products (
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    product_name VARCHAR(100) NOT NULL,
    category_id INT,
    price DECIMAL(10,2),
    stock INT,
    FOREIGN KEY (category_id)
    REFERENCES categories(category_id)
);

-- 4. Create Orders Table
CREATE TABLE orders (
    order_id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT,
    order_date DATE,
    status VARCHAR(30),
    FOREIGN KEY (customer_id)
    REFERENCES customers(customer_id)
);

-- 5. Create Order Items Table
CREATE TABLE order_items (
    order_item_id INT PRIMARY KEY AUTO_INCREMENT,
    order_id INT,
    product_id INT,
    quantity INT,
    unit_price DECIMAL(10,2),
    FOREIGN KEY (order_id)
    REFERENCES orders(order_id),
    FOREIGN KEY (product_id)
    REFERENCES products(product_id)
);

-- 6. Create Payments Table
CREATE TABLE payments (
    payment_id INT PRIMARY KEY AUTO_INCREMENT,
    order_id INT,
    payment_date DATE,
    amount DECIMAL(10,2),
    payment_status VARCHAR(30),
    FOREIGN KEY (order_id)
    REFERENCES orders(order_id)
);

-- Insert Customers
INSERT INTO customers
(customer_name, email, city)
VALUES
('Rahul Sharma', 'rahul@gmail.com', 'Pune'),
('Amit Patil', 'amit@gmail.com', 'Mumbai'),
('Priya Shah', 'priya@gmail.com', 'Nashik'),
('Sneha More', 'sneha@gmail.com', 'Dhule'),
('Karan Joshi', 'karan@gmail.com', 'Pune');

-- Insert Categories
INSERT INTO categories (category_name)
VALUES
('Electronics'),
('Clothing'),
('Books'),
('Home Appliances');

-- Insert Products
INSERT INTO products
(product_name, category_id, price, stock)
VALUES
('Laptop', 1, 55000, 10),
('Mobile', 1, 20000, 15),
('T-Shirt', 2, 800, 30),
('Jeans', 2, 1500, 20),
('SQL Book', 3, 600, 25),
('Mixer', 4, 2500, 5),
('Python Book', 3, 750, 0);

-- Insert Orders
INSERT INTO orders
(customer_id, order_date, status)
VALUES
(1, '2026-10-01', 'Completed'),
(2, '2026-10-02', 'Completed'),
(1, '2026-10-05', 'Pending'),
(3, '2026-10-06', 'Cancelled'),
(4, '2026-10-08', 'Completed');

-- Insert Order Items
INSERT INTO order_items
(order_id, product_id, quantity, unit_price)
VALUES
(1, 1, 1, 55000),
(1, 5, 2, 600),
(2, 2, 1, 20000),
(2, 3, 2, 800),
(3, 4, 1, 1500),
(4, 6, 1, 2500),
(5, 5, 3, 600),
(5, 3, 1, 800);

-- Insert Payments
INSERT INTO payments
(order_id, payment_date, amount, payment_status)
VALUES
(1, '2026-10-01', 56200, 'Paid'),
(2, '2026-10-02', 21600, 'Paid'),
(3, '2026-10-05', 1500, 'Pending'),
(4, '2026-10-06', 2500, 'Failed'),
(5, '2026-10-08', 2600, 'Paid');

-- Display All Tables
SHOW TABLES;

-- Display Table Data
SELECT * FROM customers;
SELECT * FROM categories;
SELECT * FROM products;
SELECT * FROM orders;
SELECT * FROM order_items;
SELECT * FROM payments;
