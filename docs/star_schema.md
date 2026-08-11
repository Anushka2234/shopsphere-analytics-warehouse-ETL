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
