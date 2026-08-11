# ShopSphere Analytics Warehouse – Dataset Reference

## 1. Purpose

This document provides a technical reference for the source datasets used in the ShopSphere Analytics Warehouse.

It serves as a quick-reference catalog for understanding:

- Available source datasets
- Business purpose
- Expected data grain
- Primary business keys
- Major relationships
- Analytical usage
- Warehouse mapping

The source datasets will initially be ingested into the Raw Layer without modification and subsequently processed through the Staging and Warehouse layers.

---

# 2. Source Dataset Inventory

ShopSphere uses eight primary source datasets:

1. Customers
2. Sellers
3. Products
4. Orders
5. Order Items
6. Payments
7. Reviews
8. Geolocation

---

# 3. Dataset Summary

| Dataset | Business Area | Expected Grain | Primary Business Key | Main Purpose |
|---|---|---|---|---|
| Customers | Customer | One row per customer | customer_id | Customer information |
| Sellers | Seller | One row per seller | seller_id | Seller information |
| Products | Product | One row per product | product_id | Product information |
| Orders | Sales / Operations | One row per order | order_id | Order lifecycle |
| Order Items | Sales | One row per order-product line | order_id + order_item_id | Products purchased |
| Payments | Finance | One row per payment record | Order/payment combination | Payment information |
| Reviews | Customer Experience | One row per review | review_id / equivalent | Customer feedback |
| Geolocation | Geography | One row per geographic record | Postal/geographic key | Geographic information |

> Note: The exact keys and grain will be validated against the actual source files during the data profiling stage.

---

# 4. Customers Dataset

## Dataset Name

`customers`

## Business Area

Customer Management

## Purpose

Contains information about customers who purchase products through the ShopSphere marketplace.

## Expected Grain

One row per customer.

## Business Key

```text
customer_id
