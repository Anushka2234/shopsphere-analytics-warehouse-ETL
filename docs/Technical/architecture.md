# ShopSphere Analytics Warehouse – Data Warehouse Architecture

## 1. Purpose

This document defines the technical architecture of the ShopSphere Analytics Warehouse.

The architecture describes how operational e-commerce source data is ingested, stored, cleaned, transformed, modeled, and exposed for analytical reporting.

The architecture is designed to provide:

- Reliable data processing
- Data quality management
- Separation of responsibilities
- Historical analytical capability
- Scalable data processing
- Reusable analytical datasets
- Power BI-ready data

---

# 2. Architecture Overview

The ShopSphere Analytics Warehouse follows a layered data architecture.

```text
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

┌──────────────────────────────────────────┐
│              SOURCE SYSTEM               │
│                                          │
│              CSV Files                   │
│                                          │
│  Customers | Orders | Products | Sellers │
│  Payments  | Reviews | Geolocation       │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│                RAW LAYER                 │
│                                          │
│              SQL Server                  │
│              Schema: raw                 │
│                                          │
│     Original source data                │
│     No business transformation          │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│             STAGING LAYER                │
│                                          │
│              SQL Server                  │
│            Schema: staging               │
│                                          │
│  Cleaning | Standardization | Validation │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│          TRANSFORMATION LAYER            │
│                                          │
│         Business Transformation          │
│                                          │
│  Business Rules | Calculations | Keys    │
│  Dimension Preparation | Fact Preparation│
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│            DATA WAREHOUSE                │
│                                          │
│              SQL Server                  │
│               Schema: dw                 │
│                                          │
│             Star Schema                  │
│                                          │
│  Dimensions + Fact Tables                │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│             ANALYTICS LAYER              │
│                                          │
│       SQL Views | KPIs | Aggregations    │
│       Advanced Analytical Queries        │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│              REPORTING                   │
│                                          │
│                 Power BI                 │
│                                          │
│ Executive | Sales | Customer | Product   │
│ Operations Dashboards                    │
└──────────────────────────────────────────┘
