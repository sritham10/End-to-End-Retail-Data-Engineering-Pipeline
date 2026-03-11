
# End-to-End Retail Data Engineering Pipeline

## Overview

This project implements an **end-to-end retail data engineering pipeline** using **Databricks, PySpark, SQL, and Delta Lake** following the **Medallion Architecture (Bronze → Silver → Gold)**.

The pipeline ingests raw CSV data, performs data quality validation and business logic checks, and transforms the data into structured analytics-ready datasets.

---

## Architecture

Data flows through the following stages:

CSV Files  
↓  
Bronze Layer (Raw Delta Tables)  
↓  
Data Profiling & Data Quality Checks  
↓  
Business Logic Validation  
↓  
Silver Layer Transformations  
↓  
Analytics-Ready Tables

---

## Tech Stack

- Databricks
- PySpark
- SQL
- Delta Lake
- GitHub

---

## Dataset

**Brazilian E-Commerce Public Dataset (Olist)**

This dataset contains information about:

- Orders
- Customers
- Products
- Payments
- Reviews
- Sellers
- Order Items

---

## Week 1 Implementation

**Bronze Layer & Data Quality Framework**

Implemented the following:

- Bronze layer ingestion from CSV files
- Data profiling and schema validation
- Data integrity validation
- Referential integrity checks
- Business logic validation
- Financial reconciliation checks
- Data quality validation framework
- Governance monitoring with audit logging

---

## Week 2 Implementation

**Silver Layer Transformations & SCD**

Implemented the following:

- PySpark data transformations
- Aggregated order-level datasets
- Customer Dimension Table (SCD Type-2)
- Revenue aggregation logic
- Data validation framework in PySpark
- Pipeline governance and audit logging
- Delta Lake optimization (OPTIMIZE, ZORDER, VACUUM)

---

## Data Quality Checks Implemented

- Completeness validation
- Uniqueness validation
- Referential integrity checks
- Financial reconciliation validation
- Order lifecycle validation
- Shipment delay detection
- Fulfillment delay monitoring

---

## Future Work

- Gold Layer analytics tables
- Business KPI dashboards
- Streaming data ingestion
- Automated data quality monitoring
