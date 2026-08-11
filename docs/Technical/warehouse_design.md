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
