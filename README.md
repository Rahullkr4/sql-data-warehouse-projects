
## 📊 Enterprise Sales Data Warehouse

This project demonstrates the end-to-end lifecycle of building a modern data warehouse and running advanced analytics on business data using **SQL Server (T-SQL)**. From ingesting raw datasets to designing a star schema and generating deep analytical insights — the project walks through real-world BI processes step by step.

### 🎯 Why this project?

In today’s data-driven world, organizations rely on clean and structured data to make decisions. This project simulates a realistic data pipeline to:

- design a layered architecture using the Medallion approach (bronze, silver, gold)
- implement ETL pipelines to process CRM (Customer Relationship Management) and ERP (Enterprise Resource Planning) data
- run exploratory and advanced SQL analysis for insights

### 🌐 Real-world context

A mid-sized company is trying to merge data from sales and customer systems to analyze:

- sales performance over time  
- customer behavior and segmentation  
- product-level revenue and profitability  
- key KPIs like recency, quantity sold, and AOV  

This project delivers those insights using SQL-powered data engineering and analytics.

---

## 🏗️ Data Architecture

![Data Architecture](docs/DataArchitecture.jpg)
1. **Bronze Layer**: Stores raw data as-is from the source systems. Data is ingested from CSV Files into SQL Server Database.
2. **Silver Layer**: This layer includes data cleansing, standardization, and normalization processes to prepare data for analysis.
3. **Gold Layer**: Houses business-ready data modeled into a star schema required for reporting and analytics.

---

## 🧭 Project Overview

This project demonstrates a complete data warehousing and analytics pipeline using SQL Server. It focuses on transforming raw sales and customer data into clean, structured datasets that support deep business analysis.

The process includes:

- Designing a layered data warehouse using the Medallion Architecture (bronze, silver, gold)
- Implementing ETL pipelines to extract, clean, and load data from multiple source systems
- Building a star schema with fact and dimension tables for optimized analytical queries
- Running exploratory and advanced SQL analysis to extract meaningful insights from the gold layer.

---

## 📋 Project Requirements

This project is split into two key domains — building the data warehouse (data engineering) and performing analysis (data analytics). Each component plays a role in transforming raw data into reliable business insights.

---

#### 1. 🏗️ Data Engineering — Building the Data Warehouse

**Objective:**  
Design and implement a modern data warehouse using SQL Server that integrates and transforms data from multiple business systems to support decision-making.

**Key Deliverables:**

- **Source Data Ingestion:**  
  - Load raw data from two business systems (ERP and CRM), both provided as CSV files.
  - Maintain the raw format in the bronze layer without transformation for auditability.

- **Data Quality & Cleansing:**  
  - Detect and handle missing values, inconsistent formats, and duplicates.
  - Standardize field values (e.g., country codes, date formats, product categories).

- **Data Transformation (Silver Layer):**  
  - Normalize and join related datasets (e.g., customer data from CRM + transaction data from ERP).
  - Ensure referential integrity between keys across tables.

- **Star Schema Modeling (Gold Layer):**  
  - Design and create fact and dimension tables.
  - Implement surrogate keys, date dimensions, and type consistency for fast querying.
  - Focus on a sales-centric star schema: `fact_sales` + related dimensions (`dim_customers`, `dim_products`, etc.)

- **Scope Consideration:**  
  - Work with the latest snapshot of data.
  - No requirement for historization or slowly changing dimensions in this project.

- **Documentation:**  
  - Prepare entity-relationship diagrams and flowcharts to explain the pipeline clearly.
  - Maintain a data catalog to define the structure and semantics of all tables and fields.

---
## 📁 Repository Structure
```plaintext
Enterprise-Sales-Data-WareHouse/
│
├── datasets/                           # Raw datasets used for the project (ERP and CRM data)
│
├── docs/                               # Project documentation and architecture diagrams
│   ├── Data_Architecture.drawio        # Medallion architecture (Bronze, Silver, Gold)
│   ├── Data_Architecture.drawio.png
│   ├── Data Flow Diagram.drawio        # Full ETL/data movement pipeline
│   ├── Data Flow Diagram.drawio.png
│   ├── Integration Model.drawio        # How ERP & CRM data are merged and structured
│   ├── Integration Model.drawio.png
│   ├── Star Schema (Data Mart).drawio  # Final analytical data model for reporting
│   ├── Data Catalog.md                 # Describes tables, fields, types, and business meaning
│   ├── Naming Convention.md            # Consistent naming standards across tables and files
│
├── scripts/                            # SQL scripts for ETL and data modeling
│   ├── bronze/                         # Load raw ERP & CRM data into staging tables
│   ├── silver/                         # Clean, normalize, and join datasets for unified structure
│   ├── gold/                           # Build final fact and dimension tables (star schema)
│
├── tests/                              # Data quality checks (nulls, duplicates, referential integrity)
│
├── README.md                           # Project overview, architecture, and instructions
└── LICENSE                             # License information (MIT)
```
---

## ⚙️ Tech Stack

This project is built entirely on SQL-based technologies and leverages industry-standard practices in data warehousing and analytics.

#### Core Tools & Platforms

- **SQL Server (SSMS):**
  - Used to create and manage the entire data warehouse.
  - Handles raw data ingestion, transformation pipelines, schema modeling, and analytical queries.

- **T-SQL (Transact-SQL):**
  - The primary language for data manipulation, transformation logic, and analytical computation.
  - Used for writing all ETL scripts and advanced analysis queries.

- **CSV Files (ERP and CRM):**
  - Flat files that serve as source systems for the warehouse.
  - Contain structured sales, customer, and product data.

- **draw.io (Diagrams):**
  - Used to design data flow diagrams, architecture blueprints, and entity-relationship models.
  - Helps document and visualize the data pipeline.

- **Markdown / GitHub:**
  - All documentation is written in Markdown for easy viewing.
  - Repository is organized with clear folder structures and script segregation.

#### Optional Tools (Not included in this project but compatible):

- **Power BI / Tableau / Excel:**  
  - The gold layer is designed to plug into any BI tool for dashboards and reports.
  - Dimensional modeling ensures compatibility with self-service analytics platforms.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and share this project with proper attribution.

---

## 🌟 About

Hi there! I'm **Rahul Kumar**, an aspiring **Data Analyst and Data Engineer** with a passion for transforming raw data into meaningful insights. I enjoy working with **SQL, Python, Power BI, and Excel** to build data-driven solutions and solve real-world business problems.

This project reflects my commitment to continuous learning and applying industry best practices in data engineering and analytics. I'm currently focused on building portfolio projects and preparing for opportunities in the data domain.

---
