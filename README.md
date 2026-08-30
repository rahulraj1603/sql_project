# sql_project

## Overview
This project contains SQL scripts for setting up and managing an **ecommerce database** called `harryshop`. It includes database schema creation, sample data population, and analytical queries.

## Database Structure

### Tables

#### 1. **customers**
- `customer_id` (INT, PRIMARY KEY, AUTO_INCREMENT)
- `name` (VARCHAR(100))
- `email` (VARCHAR(150), UNIQUE)
- `city` (VARCHAR(50))
- `signup_date` (DATE)

#### 2. **products**
- `product_id` (INT, PRIMARY KEY, AUTO_INCREMENT)
- `product_name` (VARCHAR(100))
- `category` (VARCHAR(50))
- `price` (DECIMAL(10,2))
- `stock` (INT)

#### 3. **orders**
- `order_id` (INT, PRIMARY KEY, AUTO_INCREMENT)
- `customer_id` (INT, FOREIGN KEY)
- `order_date` (DATE)
- `order_status` (VARCHAR(30)) - Delivered, Pending, Cancelled

#### 4. **order_items**
- `order_item_id` (INT, PRIMARY KEY, AUTO_INCREMENT)
- `order_id` (INT, FOREIGN KEY)
- `product_id` (INT, FOREIGN KEY)
- `quantity` (INT)

#### 5. **payments**
- `payment_id` (INT, PRIMARY KEY, AUTO_INCREMENT)
- `order_id` (INT, FOREIGN KEY)
- `payment_mode` (VARCHAR(30)) - UPI, Credit Card, Debit Card
- `amount` (DECIMAL(10,2))
- `payment_date` (DATE)

## Files

### 1. `ecommerce_tables.sql`
Creates the `harryshop` database and all tables with proper schema, relationships, and constraints.

### 2. `ecommerce_populate_tables.sql`
Populates the database with sample data:
- 20 customers from various Indian cities
- 20 tech-related products (hoodies, mugs, stickers, etc.)
- 20 orders with various statuses
- Order items linking orders to products
- Payment records for all orders

### 3. `Analysis_Queries.sql`
Contains analytical SQL queries including:
- Total revenue calculation
- Revenue by product (delivered orders only)
- Customer spending analysis
- Best-selling products
- Cancelled orders count

## Setup Instructions

1. Run `ecommerce_tables.sql` to create the database and tables
2. Run `ecommerce_populate_tables.sql` to insert sample data
3. Run queries from `Analysis_Queries.sql` for analysis and reporting

