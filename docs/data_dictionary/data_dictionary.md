# ShopSphere Analytics Warehouse – Data Dictionary

## 1. Purpose

The Data Dictionary provides a detailed reference for the source data used in the ShopSphere Analytics Warehouse.

It documents:

- Dataset names
- Column names
- Data types
- Business meaning
- Key information
- Nullable expectations
- Analytical usage

The Data Dictionary will be used as a reference during:

- Data profiling
- Raw table creation
- Staging transformation
- Warehouse modeling
- ETL development
- SQL analytics
- Power BI development

> Note: Source data types and nullability will be validated against the actual CSV files during Phase 2.

---

# 2. Data Type Convention

The source datasets are CSV files. Therefore, the original files do not enforce database data types.

During Raw Layer ingestion, appropriate SQL Server data types will be assigned.

Typical data types used in the warehouse include:

| Data Type | Typical Usage |
|---|---|
| `VARCHAR` | Identifiers and text |
| `INT` | Integer values |
| `DECIMAL` | Monetary and numeric measurements |
| `DATE` | Date values |
| `DATETIME2` | Date and timestamp values |
| `FLOAT` / `DECIMAL` | Geographic coordinates |
| `BIT` | Boolean indicators |

Final SQL Server data types will be determined during database development.

---

# 3. Customers Dataset

## Dataset

`customers`

## Grain

One row per customer record.

| Column | Expected Data Type | Key | Description |
|---|---|---|---|
| `customer_id` | VARCHAR | Business Identifier | Identifier of the customer record associated with an order |
| `customer_unique_id` | VARCHAR | Business Key | Unique identifier representing the underlying customer |
| `customer_zip_code_prefix` | INT | Foreign/Location Reference | Postal code prefix associated with the customer |
| `customer_city` | VARCHAR | Attribute | Customer city |
| `customer_state` | VARCHAR | Attribute | Customer state |

### Key Notes

`customer_id` is used to connect the customer record to the Orders dataset.

`customer_unique_id` represents the unique customer identity and is important for customer-level analysis, including repeat-customer analysis.

### Analytical Usage

- Customer count
- Customer revenue
- Repeat customer analysis
- Customer location analysis
- Customer purchasing behavior

---

# 4. Sellers Dataset

## Dataset

`sellers`

## Grain

One row per seller.

| Column | Expected Data Type | Key | Description |
|---|---|---|---|
| `seller_id` | VARCHAR | Business Key | Unique seller identifier |
| `seller_zip_code_prefix` | INT | Location Reference | Seller postal code prefix |
| `seller_city` | VARCHAR | Attribute | Seller city |
| `seller_state` | VARCHAR | Attribute | Seller state |

### Analytical Usage

- Seller performance
- Seller revenue
- Seller order volume
- Seller ranking
- Seller geographic analysis

---

# 5. Products Dataset

## Dataset

`products`

## Grain

One row per product.

| Column | Expected Data Type | Key | Description |
|---|---|---|---|
| `product_id` | VARCHAR | Business Key | Unique product identifier |
| `product_category_name` | VARCHAR | Attribute | Product category |
| `product_name_lenght` | INT | Attribute | Length of the product name |
| `product_description_lenght` | INT | Attribute | Length of the product description |
| `product_photos_qty` | INT | Attribute | Number of product photos |
| `product_weight_g` | DECIMAL | Measure | Product weight in grams |
| `product_length_cm` | DECIMAL | Measure | Product length in centimeters |
| `product_height_cm` | DECIMAL | Measure | Product height in centimeters |
| `product_width_cm` | DECIMAL | Measure | Product width in centimeters |

> Note: The source dataset uses the spelling `lenght` in the column names. We will decide during the Staging Layer whether to retain the source name or standardize it to `length`.

### Analytical Usage

- Product performance
- Product category analysis
- Product attribute analysis
- Product sales analysis
- Product quality analysis

---

# 6. Orders Dataset

## Dataset

`orders`

## Grain

One row per order.

| Column | Expected Data Type | Key | Description |
|---|---|---|---|
| `order_id` | VARCHAR | Business Key | Unique order identifier |
| `customer_id` | VARCHAR | Foreign Key | Customer associated with the order |
| `order_status` | VARCHAR | Attribute | Current/status state of the order |
| `order_purchase_timestamp` | DATETIME2 | Date/Time | Date and time when the order was placed |
| `order_approved_at` | DATETIME2 | Date/Time | Date and time when the order was approved |
| `order_delivered_carrier_date` | DATETIME2 | Date/Time | Date when the order was handed to the carrier |
| `order_delivered_customer_date` | DATETIME2 | Date/Time | Date when the order was delivered to the customer |
| `order_estimated_delivery_date` | DATETIME2 | Date/Time | Estimated delivery date |

### Important Relationships

```text
orders.customer_id
        ↓
customers.customer_id
