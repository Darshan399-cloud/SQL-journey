# E-Commerce Database Structure

## 1. Customers Table
Stores customer details.

Columns:
- customer_id
- customer_name
- email
- city

## 2. Categories Table
Stores product categories.

Columns:
- category_id
- category_name

## 3. Products Table
Stores product information.

Columns:
- product_id
- product_name
- category_id
- price
- stock

## 4. Orders Table
Stores customer order information.

Columns:
- order_id
- customer_id
- order_date
- status

## 5. Order Items Table
Stores products included in each order.

Columns:
- order_item_id
- order_id
- product_id
- quantity
- unit_price

## 6. Payments Table
Stores payment details.

Columns:
- payment_id
- order_id
- payment_date
- amount
- payment_status

## Relationships
- One customer can place multiple orders.
- One category can contain multiple products.
- One order can contain multiple order items.
- One product can appear in multiple order items.
- One order can have multiple payment records.

## Important Concepts
- Primary Key uniquely identifies each record.
- Foreign Key connects related tables.
- JOIN combines records from multiple tables.
- GROUP BY groups records for calculations.