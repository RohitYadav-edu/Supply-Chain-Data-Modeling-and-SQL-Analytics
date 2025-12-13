# SwiftLogix Supply Chain Database Design & Analysis

## Overview
This project focuses on designing and implementing a relational database to model real-world supply chain and logistics operations. The goal is to transform a large, unstructured dataset into a well-organized database that supports meaningful analysis of orders, products, customers, and logistics performance.

The project follows an end-to-end data workflow — starting from raw data extraction and cleaning, moving through conceptual and physical data modeling, and ending with SQL-based querying, stored procedures, and functions for analytics.

---

## Problem Statement
Supply chain and logistics data is often large, complex, and difficult to analyze when stored in flat files. Without proper structure, answering questions related to customer behavior, order performance, profitability, or delivery efficiency becomes inefficient and error-prone.

This project addresses that problem by:
- Designing a normalized relational database
- Enforcing data integrity using primary and foreign keys
- Enabling efficient querying for operational and analytical insights

---

## Dataset
The dataset used in this project contains detailed supply chain transaction data, including:
- Orders and order items
- Product and category information
- Customer details
- Shipping and delivery metrics
- Profitability and sales measures

The raw dataset was initially provided as a single file and later split into multiple entity-specific files during data preparation.

---

## Tools & Technologies
- **Python (Pandas, Jupyter Notebook)** – Data cleaning, transformation, and table generation  
- **MySQL & MySQL Workbench** – Database creation, data loading, and querying  
- **SQL** – Table definitions, joins, subqueries, aggregations  
- **GitHub** – Version control and project documentation  

---

## Data Modeling Approach

### Conceptual Model
The conceptual model identifies key business entities and their relationships:
- Customers place Orders
- Orders contain multiple Products
- Products belong to Categories
- Categories belong to Departments

Since one order can include multiple products and a product can appear in many orders, a **many-to-many relationship** exists between Orders and Products. This is resolved using a junction table (`Order_items`).

---

### Physical Data Model
The physical model consists of six tables:
- Departments  
- Categories  
- Products  
- Customers  
- Orders  
- Order_items (junction table)

Each table includes:
- Proper primary keys
- Foreign key relationships
- Carefully selected datatypes
- NOT NULL constraints where appropriate to ensure data integrity

Datatypes were adjusted after exploring and cleaning the data to ensure accurate storage of dates, monetary values, and identifiers.

---

## Data Preparation
Data cleaning and preparation were performed in Python using Pandas:
- Column selection and renaming
- Removal of invalid or incomplete records
- Datatype standardization
- Splitting the dataset into table-specific CSV files

This step ensured compatibility with MySQL constraints and minimized data-loading errors.

---

## Database Implementation
The database was created in MySQL with:
- Enforced referential integrity
- Controlled load order to satisfy foreign key constraints
- Successful bulk data imports using MySQL Workbench and LOAD DATA INFILE

---

## SQL Queries & Analysis
The project includes:
- Basic SELECT queries ordered by primary keys
- INNER JOIN and LEFT JOIN queries across multiple tables
- Single-row and multi-row subqueries
- Aggregation queries using GROUP BY
- Conditional logic using CASE
- Subqueries using NOT IN and NOT EXISTS

These queries demonstrate how structured data enables efficient business insights.

---

## Stored Procedures & Functions
To extend database functionality:

### Stored Procedures
1. **Monthly Sales Summary** – Generates order, profit, and delivery metrics for a given month  
2. **Customer Order History** – Returns aggregated order and item-level details for a specific customer  

### Functions
1. **Profit Margin Function** – Calculates profit percentage per order  
2. **Net Item Value Function** – Computes net revenue per order item after discounts  

These improve reusability, readability, and performance of analytical queries.

---

## Key Outcomes & Benefits
- Converts raw supply chain data into a scalable relational database
- Enables faster and more reliable analytics
- Demonstrates real-world database design principles
- Supports business decision-making related to pricing, delivery risk, and profitability

---

## How This Project Helps
This database design can be directly applied to real logistics and e-commerce systems to:
- Track order performance
- Identify late delivery risks
- Analyze customer purchasing behavior
- Evaluate product and category profitability

---

## Author
**Rohit Yadav**  
Graduate Student – Information Management  
Database Design & Prototyping Project
