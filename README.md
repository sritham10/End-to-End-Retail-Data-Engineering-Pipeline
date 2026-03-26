# 🚀 End-to-End Retail Data Engineering Pipeline

---

## 📌 Overview

This project implements a **production-grade end-to-end data engineering pipeline** using:

* Databricks (PySpark + SQL)
* Delta Lake
* Azure Data Factory (ADF)

The pipeline follows the **Medallion Architecture (Bronze → Silver → Gold)** to transform raw e-commerce data into **business-ready analytical datasets**.

---

## 🏗️ Architecture

```
Raw CSV Data
↓
Bronze Layer (Raw Ingestion)
↓
Data Quality Validation
↓
Silver Layer (Clean & Structured)
↓
ADF Pipeline (Orchestration)
↓
Gold Layer (Analytics)
↓
Data Warehouse (Star Schema)
↓
BI / Reporting
```

---

## ⚙️ Tech Stack

| Category        | Tools              |
| --------------- | ------------------ |
| Compute         | Databricks         |
| Processing      | PySpark            |
| Querying        | SQL                |
| Storage         | Delta Lake         |
| Orchestration   | Azure Data Factory |
| Version Control | GitHub             |

---

## 📊 Dataset

**Brazilian E-Commerce Dataset (Olist)**

Includes:

* Orders
* Customers
* Products
* Sellers
* Payments
* Reviews
* Order Items

---

# 📅 Week 1 – Task 1 (Bronze Layer & Data Quality Framework)

### ✔️ Implemented

* CSV ingestion → Delta tables
* Schema validation & data profiling
* Data integrity validation
* Referential integrity checks
* Business rule validation
* Financial reconciliation checks
* Data quality framework
* Audit logging (`validation_audit`)

---

# 📅 Week 2 – Task 2 (SCD + Transformations in PySpark)

### ✔️ Implemented

* PySpark data transformations
* Order-level aggregations
* **Slowly Changing Dimension (SCD Type-2)**
* Customer dimension table creation
* Revenue aggregation logic
* Data validation framework
* Governance & audit logging

### ⚡ Delta Optimization

* OPTIMIZE
* ZORDER
* VACUUM

---

## 🧠 SCD Type-2 Example

| customer_id | state | start_date | end_date |
| ----------- | ----- | ---------- | -------- |
| C1          | KA    | 2023       | NULL     |
| C1          | MH    | 2022       | 2023     |

👉 Maintains historical customer changes

---

# 📅 Week 2 – Task 3 (ADF Pipeline & Orchestration)

### ✔️ Implemented

* Built ADF pipelines for ingestion & transformation
* Configured multiple **Copy Activities**:

  * orders, customers, products, sellers, payments, reviews, order_items
* Implemented **Data Flow transformations**
* Orchestrated end-to-end pipeline execution

---

## 🔄 ADF Pipeline Flow

### Bronze Ingestion

```
Multiple Copy Activities
→ Load CSV → Bronze Tables
```

### Silver Transformation

```
Orders Source
↓
Filter Nulls
↓
Add Columns
↓
Aggregate Orders
↓
Silver Sink
```

---

## 🎯 ADF Explanation

> ADF is used to orchestrate data pipelines, where raw data is ingested into Bronze layer using copy activities and transformed into structured Silver datasets using data flows.

---

# 📅 Week 3 – Task 4 (Gold Layer + Data Warehouse + Data Mesh)

## 🔹 Gold Layer Aggregations

Created analytics tables:

| Table                          | Purpose               |
| ------------------------------ | --------------------- |
| gold_customer_revenue          | Customer segmentation |
| gold_monthly_revenue           | Revenue trends        |
| gold_seller_performance        | Seller ranking        |
| gold_delivery_kpi              | Delivery performance  |
| gold_order_status_distribution | Operational health    |

---

## 🏗️ Data Warehouse (Star Schema)

```
fact_orders (central fact table)

dim_customers
dim_products
dim_sellers
dim_dates
```

### ✔️ Why Star Schema?

* Faster queries
* Simpler joins
* Optimized for BI tools

---

## 🌐 Data Mesh Implementation

| Domain    | Table                 | Business Value           |
| --------- | --------------------- | ------------------------ |
| Orders    | mesh_orders_domain    | Order lifecycle tracking |
| Customer  | mesh_customer_domain  | Customer segmentation    |
| Seller    | mesh_seller_domain    | Seller performance       |
| Logistics | mesh_logistics_domain | Delivery tracking        |

---

## 🛡️ Governance

* Audit logging for all tables
* OPTIMIZE + VACUUM applied
* Ensures performance & traceability

---

# 📅 Week 3 – Task 5 (Dynamic Table Creation)

## 🔹 Implementation

* Created **mapping table** (table_name + location)
* Implemented **parameter-driven notebook**
* Validated table existence
* Generated dynamic **CREATE TABLE statements**
* Created Delta tables automatically

---

## 🔄 Flow

```
Input Table Name
↓
Check Mapping Table
↓
If Exists → Create Table
Else → Error
```

---

## 🎯 Key Concept

👉 Metadata-driven pipelines (used in real production systems)

---

# 📅 Week 4 – Task 6 (Reusable PySpark Package)

## 🔹 Implementation

* Created reusable Python package `olist_utils`
* Built Python wheel (.whl) for deployment
* Modularized:

  * Data quality functions
  * Business KPI functions
  * Metadata utilities
* Installed and consumed package in Databricks notebooks

---

## 📐 Package Architecture

```
olist_utils/
│
├── transformations.py
├── __init__.py
├── setup.py
```

---

## ❓ Why Packaging?

Instead of writing PySpark logic repeatedly in notebooks, the package ensures:

* Reusability across pipelines
* Standardization of business logic
* Faster development and debugging

---

## 🚀 Deployment

The wheel file was installed using Databricks `%pip install` and can be attached as a cluster library for production use.

---

# 📊 Data Quality Framework

* Completeness validation
* Uniqueness validation
* Referential integrity checks
* Financial reconciliation
* Order lifecycle validation
* Shipment delay detection
* Fulfillment delay monitoring

---

# 💡 Key Concepts Covered

* Medallion Architecture
* SCD Type-2
* Data Warehouse (Star Schema)
* Data Mesh
* Data Quality Engineering
* ADF Orchestration
* Delta Lake Optimization
* Metadata-driven pipelines
* Code modularization & packaging

---

# 📈 Business Impact

* Enables reliable analytics
* Improves data trust
* Supports BI dashboards
* Ensures scalable architecture
* Automates pipelines

---

# 🔮 Future Enhancements

* Power BI dashboards
* Real-time streaming pipelines
* Advanced monitoring & alerting
* Data catalog integration

---

# 🧠 Key Highlights

✔ End-to-end pipeline
✔ SCD Type-2 implementation
✔ ADF orchestration
✔ Star Schema design
✔ Data Mesh architecture
✔ Dynamic table creation
✔ Reusable PySpark package
✔ Production-ready design

---

# 👨‍💻 Author

**Sritham Choudhury**
Data Engineer | Databricks | PySpark | SQL

---

# ⭐ Final Note

> This project demonstrates how raw data is transformed into high-quality, scalable, and business-ready insights using modern data engineering practices.

---

