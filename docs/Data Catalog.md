# Data Catalog for Gold Layer

## Overview

The Gold Layer is the business-level data representation, structured to support analytical and reporting use cases. It consists of dimension tables and fact tables for customer and sales analysis.

---

## 1. gold.dim_customers

- **Purpose:** Stores customer details enriched with demographic and geographic data.
- **Columns:**

| Column Name | Data Type | Description |
|------------|------------|-------------|
| customer_key | INT | Surrogate key uniquely identifying each customer record. |
| customer_id | INT | Unique customer identifier assigned to each customer. |
| customer_name | NVARCHAR(100) | Full name of the customer. |
| gender | NVARCHAR(20) | Gender of the customer. |
| city | NVARCHAR(50) | City where the customer resides. |
| state | NVARCHAR(50) | State where the customer resides. |
| country | NVARCHAR(50) | Country where the customer resides. |
| signup_date | DATE | Date when the customer registered. |

---

## 2. gold.dim_products

- **Purpose:** Provides information about products and their attributes.
- **Columns:**

| Column Name | Data Type | Description |
|------------|------------|-------------|
| product_key | INT | Surrogate key uniquely identifying each product record. |
| product_id | INT | Unique identifier assigned to the product. |
| product_name | NVARCHAR(100) | Name of the product. |
| category | NVARCHAR(50) | Product category. |
| sub_category | NVARCHAR(50) | Product sub-category. |
| brand | NVARCHAR(50) | Product brand name. |
| unit_price | DECIMAL(10,2) | Selling price of the product. |
| launch_date | DATE | Date when the product was launched. |

---

## 3. gold.fact_sales

- **Purpose:** Stores transactional sales data for analytical purposes.
- **Columns:**

| Column Name | Data Type | Description |
|------------|------------|-------------|
| sales_id | INT | Unique identifier for each sales transaction. |
| customer_key | INT | Foreign key referencing customer dimension. |
| product_key | INT | Foreign key referencing product dimension. |
| sale_date | DATE | Date when the sale occurred. |
| quantity | INT | Number of units sold. |
| sales_amount | DECIMAL(12,2) | Total revenue generated from the transaction. |
| discount | DECIMAL(5,2) | Discount applied to the sale. |
| profit | DECIMAL(12,2) | Profit earned from the transaction. |

---

## Business Metrics

### Total Sales

```sql
SELECT SUM(sales_amount) AS total_sales
FROM gold.fact_sales;
```

### Total Profit

```sql
SELECT SUM(profit) AS total_profit
FROM gold.fact_sales;
```

### Total Orders

```sql
SELECT COUNT(DISTINCT sales_id) AS total_orders
FROM gold.fact_sales;
```

### Customer Count

```sql
SELECT COUNT(DISTINCT customer_key) AS total_customers
FROM gold.fact_sales;
```

### Average Order Value

```sql
SELECT SUM(sales_amount) / COUNT(DISTINCT sales_id) AS average_order_value
FROM gold.fact_sales;
```
