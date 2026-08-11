# ShopSphere Analytics Warehouse – Warehouse Design

## 1. Purpose

This document defines the logical design of the ShopSphere Analytics Warehouse.

The warehouse design translates the business requirements, reporting requirements, source analysis, and architecture into a structured dimensional model.

The design defines:

- Fact tables
- Dimension tables
- Table grain
- Business keys
- Surrogate keys
- Foreign keys
- Measures
- Attributes
- Relationships
- Source-to-warehouse mappings

The warehouse will be implemented in SQL Server using a Star Schema.

---

# 2. Warehouse Schema

The analytical warehouse will use the following SQL Server schema:

```text
dw

                    ┌───────────────┐
                    │   dim_date    │
                    └───────┬───────┘
                            │
                            │
                            ▼
┌────────────────┐   ┌───────────────┐   ┌────────────────┐
│ dim_customer   │──►│  fact_sales   │◄──│  dim_product   │
└────────────────┘   └───────┬───────┘   └────────────────┘
                              │
                              │
                              ▼
                       ┌───────────────┐
                       │   dim_seller  │
                       └───────────────┘


                        ┌─────────────────────┐
                        │      dim_date       │
                        │─────────────────────│
                        │ date_key PK         │
                        │ full_date           │
                        │ day                 │
                        │ month               │
                        │ quarter             │
                        │ year                │
                        └──────────┬──────────┘
                                   │
                                   │
                                   │
┌─────────────────────┐            │            ┌─────────────────────┐
│    dim_customer     │            │            │     dim_product     │
│─────────────────────│            │            │─────────────────────│
│ customer_key PK     │            │            │ product_key PK      │
│ customer_unique_id  │            │            │ product_id          │
│ customer_city       │            │            │ category            │
│ customer_state      │            │            │ product attributes  │
└──────────┬──────────┘            │            └──────────┬──────────┘
           │                       │                       │
           │                       │                       │
           │                ┌──────▼──────┐                │
           └───────────────►│ fact_sales  │◄───────────────┘
                            │──────────────│
                            │ sales_key PK │
                            │ order_id     │
                            │ order_item_id│
                            │ customer_key │
                            │ product_key  │
                            │ seller_key   │
                            │ order_date   │
                            │ shipping_date│
                            │ delivery_date│
                            │ price        │
                            │ freight_value│
                            └──────┬───────┘
                                   │
                                   │
                                   ▼
                        ┌─────────────────────┐
                        │      dim_seller     │
                        │─────────────────────│
                        │ seller_key PK       │
                        │ seller_id           │
                        │ seller_city         │
                        │ seller_state        │
                        └─────────────────────┘
