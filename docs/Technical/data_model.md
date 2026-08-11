# ShopSphere Analytics Warehouse – Star Schema Design

## 1. Purpose

This document defines the Star Schema for the ShopSphere Analytics Warehouse.

The Star Schema translates the warehouse requirements into a dimensional model optimized for:

- Business Intelligence
- Analytical SQL
- Power BI reporting
- KPI calculation
- Trend analysis
- Aggregation
- Business performance analysis

The model consists of a central Sales Fact surrounded by reusable Dimension Tables.

---

# 2. Star Schema Overview

The initial ShopSphere Star Schema consists of:

## Fact Table

```text
fact_sales

                         ┌─────────────────┐
                         │    dim_date     │
                         │─────────────────│
                         │ PK date_key     │
                         │ full_date       │
                         │ day             │
                         │ month           │
                         │ quarter         │
                         │ year            │
                         └────────┬────────┘
                                  │
                                  │
                                  ▼
┌─────────────────┐      ┌─────────────────┐      ┌─────────────────┐
│  dim_customer   │      │   fact_sales    │      │   dim_product   │
│─────────────────│      │─────────────────│      │─────────────────│
│ PK customer_key │─────►│ PK sales_key    │◄─────│ PK product_key  │
│ customer_unique │      │ order_id        │      │ product_id      │
│ customer_city   │      │ order_item_id   │      │ category        │
│ customer_state  │      │ customer_key FK │      │ attributes      │
└─────────────────┘      │ product_key FK  │      └─────────────────┘
                         │ seller_key FK   │
                         │ order_date_key  │
                         │ shipping_date   │
                         │ delivery_date   │
                         │ price           │
                         │ freight_value   │
                         └────────┬────────┘
                                  │
                                  │
                                  ▼
                         ┌─────────────────┐
                         │   dim_seller    │
                         │─────────────────│
                         │ PK seller_key   │
                         │ seller_id       │
                         │ seller_city     │
                         │ seller_state    │
                         └─────────────────┘
