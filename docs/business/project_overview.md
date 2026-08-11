# ShopSphere Analytics Warehouse

## Project Overview

ShopSphere is a fictional e-commerce marketplace that connects customers, sellers, and products through an online platform.

The business generates large volumes of transactional data related to customers, orders, order items, products, sellers, payments, reviews, and geographic locations.

The objective of this project is to design and develop an enterprise analytics data warehouse that transforms operational e-commerce data into structured and analytics-ready datasets for business intelligence and decision-making.

The project follows a layered data warehouse architecture that separates raw operational data from cleaned, transformed, and analytical data.

## Architecture Flow

Source Data

↓

Raw Layer

↓

Staging Layer

↓

Transformation Layer

↓

Data Warehouse

↓

Analytics Layer

↓

Power BI

## Business Problem

ShopSphere's operational data is distributed across multiple transactional datasets. This makes it difficult for business users to perform integrated analysis and generate reliable business insights.

The source data is not optimized for analytical reporting because:

- Data is distributed across multiple datasets.
- Analytical queries require complex joins.
- Data quality issues may exist.
- Business metrics are not centrally defined.
- Historical analysis is difficult.
- Operational datasets are not optimized for BI reporting.

## Project Goal

The goal of this project is to create a centralized analytics data warehouse that provides clean, consistent, integrated, and analytics-ready data.

The warehouse will support:

- Sales Analysis
- Customer Analysis
- Product Analysis
- Seller Analysis
- Payment Analysis
- Geographic Analysis
- Delivery Performance Analysis
- Customer Review Analysis

## Technology Stack

| Component | Technology |
|---|---|
| Database | SQL Server |
| Development Environment | SQL Server Management Studio (SSMS) |
| Source Data | CSV Files |
| Data Integration | SQL-based ETL |
| Data Modeling | Star Schema |
| Analytics | SQL Views and Advanced SQL |
| Reporting | Power BI |
| Documentation | GitHub |

## Expected Outcome

The final solution will provide an end-to-end analytics platform consisting of:

1. Source data ingestion
2. Raw data storage
3. Data profiling
4. Data cleansing and standardization
5. Transformation and business logic
6. Dimensional data warehouse
7. Analytical views and KPI calculations
8. Power BI dashboards

The project demonstrates practical skills in Data Warehousing, ETL Development, SQL, Dimensional Modeling, Data Quality Management, Advanced SQL Analytics, and Business Intelligence.
