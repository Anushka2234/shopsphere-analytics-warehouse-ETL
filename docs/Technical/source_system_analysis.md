# ShopSphere Analytics Warehouse – Source System Analysis

## 1. Purpose

The purpose of this document is to analyze the source datasets used by the ShopSphere Analytics Warehouse.

The source system analysis provides an understanding of:

- Source datasets
- Business purpose of each dataset
- Important columns
- Business keys
- Relationships between datasets
- Data dependencies
- Potential data quality issues
- Analytical relevance

This analysis will serve as the foundation for the Raw Layer, Staging Layer, Data Warehouse, and analytical model.

---

# 2. Source System Overview

ShopSphere receives its source data in the form of CSV files representing different operational areas of the e-commerce business.

The primary source datasets are:

1. Customers
2. Sellers
3. Products
4. Orders
5. Order Items
6. Payments
7. Reviews
8. Geolocation

The source data represents different aspects of the e-commerce transaction lifecycle.

---

# 3. Source Architecture

The source data follows the following logical flow:

```text
Customer
    │
    │
    ▼
Order ──────────────── Customer
    │
    │
    ├──────── Order Items ─────── Product
    │                              │
    │                              │
    │                              ▼
    │                            Seller
    │
    ├──────── Payments
    │
    └──────── Reviews ───────── Product

Customer / Seller / Location
            │
            ▼
       Geolocation
