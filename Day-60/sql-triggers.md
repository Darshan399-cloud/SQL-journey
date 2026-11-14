-- Day 60: SQL Triggers

USE ecommerce_db;

-- 1. Create an audit table
CREATE TABLE product_price_history (
    history_id INT PRIMARY KEY AUTO_INCREMENT,
    product_id INT,
    old_price DECIMAL(10,2),
    new_price DECIMAL(10,2),
    changed_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- 2. BEFORE INSERT Trigger
-- Prevent negative product prices

DELIMITER //

CREATE TRIGGER before_product_insert
BEFORE INSERT ON products
FOR EACH ROW
BEGIN
    IF NEW.price < 0 THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'Product price cannot be negative';
    END IF;
END //

DELIMITER ;

-- 3. AFTER UPDATE Trigger
-- Store product price changes in history

DELIMITER //

CREATE TRIGGER after_product_price_update
AFTER UPDATE ON products
FOR EACH ROW
BEGIN
    IF OLD.price <> NEW.price THEN
        INSERT INTO product_price_history
        (product_id, old_price, new_price)
        VALUES
        (OLD.product_id, OLD.price, NEW.price);
    END IF;
END //

DELIMITER ;

-- Test price update
UPDATE products
SET price = 56000
WHERE product_id = 1;

-- Check price history
SELECT * FROM product_price_history;


-- 4. BEFORE UPDATE Trigger
-- Prevent negative stock values

DELIMITER //

CREATE TRIGGER before_product_stock_update
BEFORE UPDATE ON products
FOR EACH ROW
BEGIN
    IF NEW.stock < 0 THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'Stock cannot be negative';
    END IF;
END //

DELIMITER ;

-- Test stock update
-- This should produce an error:
-- UPDATE products SET stock = -5 WHERE product_id = 1;


-- 5. AFTER INSERT Trigger
-- Record newly inserted orders

CREATE TABLE order_audit (
    audit_id INT PRIMARY KEY AUTO_INCREMENT,
    order_id INT,
    action_message VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

DELIMITER //

CREATE TRIGGER after_order_insert
AFTER INSERT ON orders
FOR EACH ROW
BEGIN
    INSERT INTO order_audit
    (order_id, action_message)
    VALUES
    (NEW.order_id, 'New order created');
END //

DELIMITER ;

-- Test by inserting a new order
INSERT INTO orders
(customer_id, order_date, status)
VALUES
(5, '2026-11-14', 'Pending');

-- Check order audit
SELECT * FROM order_audit;


-- 6. BEFORE DELETE Trigger
-- Prevent deletion of products that have order records

DELIMITER //

CREATE TRIGGER before_product_delete
BEFORE DELETE ON products
FOR EACH ROW
BEGIN
    IF EXISTS (
        SELECT 1
        FROM order_items
        WHERE product_id = OLD.product_id
    ) THEN
        SIGNAL SQLSTATE '45000'
        SET MESSAGE_TEXT = 'Cannot delete a product used in orders';
    END IF;
END //

DELIMITER ;

-- Test trigger
-- DELETE FROM products WHERE product_id = 1;


-- 7. Display all triggers
SHOW TRIGGERS;


-- 8. Delete a trigger
-- Run only when you want to remove it.

-- DROP TRIGGER before_product_insert;