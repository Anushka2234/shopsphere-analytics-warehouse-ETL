# ShopSphere Analytics Warehouse – Stakeholder Requirements

## 1. Purpose

The purpose of this document is to identify the key stakeholders of the ShopSphere Analytics Warehouse and define their analytical information requirements.

Understanding stakeholder requirements ensures that the data warehouse is designed around actual business needs rather than only technical requirements.

The identified requirements will be used to define:

- Business requirements
- Reporting requirements
- KPIs
- Fact and dimension tables
- Analytical views
- Power BI dashboards

---

# 2. Stakeholder Overview

The primary stakeholders for the ShopSphere Analytics Warehouse are:

1. Executive Management
2. Sales Management
3. Product Management
4. Seller Management
5. Operations Team
6. Finance Team
7. Customer Analytics Team
8. Data Analysts
9. Business Intelligence Team

---

# 3. Executive Management

## Role

Executive Management is responsible for understanding the overall health and performance of the e-commerce business.

## Key Business Questions

- What is the overall revenue?
- How many orders are being placed?
- How is sales performance changing over time?
- Which product categories generate the most revenue?
- Which regions contribute the most sales?
- Which sellers have the highest sales contribution?
- How is customer activity changing?
- Are business performance targets being achieved?

## Required Metrics

- Total Revenue
- Total Orders
- Total Customers
- Total Products
- Average Order Value
- Revenue Growth
- Orders Growth
- Top Product Categories
- Top Sellers
- Sales by Region

## Reporting Requirement

Executive Management requires a high-level executive dashboard with summary KPIs, trends, and business performance indicators.

---

# 4. Sales Management

## Role

The Sales Team is responsible for monitoring sales performance and identifying opportunities for revenue growth.

## Key Business Questions

- What are the monthly and yearly sales trends?
- Which products generate the highest sales?
- Which categories perform best?
- Which sellers generate the most revenue?
- Which locations generate the highest sales?
- What is the average order value?
- How many orders are completed?
- Which periods have the highest sales volume?

## Required Metrics

- Revenue
- Order Count
- Order Item Count
- Average Order Value
- Revenue by Product
- Revenue by Category
- Revenue by Seller
- Revenue by Location
- Monthly Revenue
- Yearly Revenue

## Reporting Requirement

Sales Management requires a Sales Performance Dashboard with trend analysis, product analysis, seller analysis, and geographic analysis.

---

# 5. Product Management

## Role

Product Management is responsible for understanding product performance and identifying high-performing and underperforming products.

## Key Business Questions

- Which products sell the most?
- Which products generate the most revenue?
- Which categories perform best?
- Which products receive the highest ratings?
- Which products have low sales?
- How does product performance change over time?

## Required Metrics

- Units Sold
- Revenue
- Order Count
- Average Product Price
- Average Rating
- Review Count
- Revenue by Category
- Sales by Product

## Reporting Requirement

Product Management requires a Product Performance Dashboard.

---

# 6. Seller Management

## Role

Seller Management monitors seller performance and contribution to the marketplace.

## Key Business Questions

- Which sellers generate the most revenue?
- Which sellers have the highest number of orders?
- Which sellers sell the most products?
- Which sellers receive the highest customer ratings?
- Which sellers contribute most to overall sales?
- How does seller performance change over time?

## Required Metrics

- Seller Revenue
- Orders by Seller
- Units Sold
- Average Order Value
- Average Rating
- Review Count
- Seller Sales Contribution
- Seller Ranking

## Reporting Requirement

Seller Management requires seller performance reporting and ranking analysis.

---

# 7. Operations Team

## Role

The Operations Team is responsible for monitoring order processing and delivery performance.

## Key Business Questions

- How many orders are being processed?
- How many orders are delivered?
- How long does delivery take?
- Which locations have longer delivery times?
- Are there delays in order delivery?
- How does delivery performance change over time?

## Required Metrics

- Total Orders
- Delivered Orders
- Cancelled Orders
- Average Delivery Time
- Delivery Performance
- Orders by Status
- Orders by Location
- Delivery Trends

## Reporting Requirement

Operations requires an Operations Performance Dashboard.

---

# 8. Finance Team

## Role

The Finance Team requires visibility into revenue, payment activity, and transaction values.

## Key Business Questions

- What is the total sales value?
- What payment methods are most commonly used?
- What is the payment value by method?
- How does payment activity change over time?
- Which payment methods contribute the highest transaction value?

## Required Metrics

- Total Payment Value
- Payment Transaction Count
- Payment Value by Method
- Payment Installments
- Revenue by Period
- Payment Distribution

## Reporting Requirement

Finance requires financial and payment analysis through SQL reports and Power BI visuals.

---

# 9. Customer Analytics Team

## Role

The Customer Analytics Team analyzes customer behavior, purchasing patterns, and customer engagement.

## Key Business Questions

- How many active customers are there?
- Which customers generate the most revenue?
- How frequently do customers purchase?
- Which locations have the highest customer activity?
- What products do customers purchase?
- Which customers are repeat purchasers?
- How does customer behavior change over time?

## Required Metrics

- Total Customers
- Active Customers
- New Customers
- Repeat Customers
- Customer Revenue
- Average Order Value
- Orders per Customer
- Customer Purchase Frequency
- Customer Lifetime Value

## Reporting Requirement

The Customer Analytics Team requires customer behavior and segmentation analysis.

---

# 10. Data Analysts

## Role

Data Analysts use the warehouse to perform detailed analysis and answer ad-hoc business questions.

## Requirements

Data Analysts require:

- Clean analytical tables
- Consistent business definitions
- Historical data
- Reusable SQL views
- Well-documented dimensions and facts
- Reliable KPIs
- Easy access to analytical datasets

## Key Analytical Capabilities

- Ad-hoc SQL analysis
- Trend analysis
- Customer analysis
- Product analysis
- Seller analysis
- Geographic analysis
- Performance analysis
- KPI analysis

---

# 11. Business Intelligence Team

## Role

The Business Intelligence Team develops and maintains Power BI dashboards and analytical reports.

## Requirements

The BI Team requires:

- Analytics-ready warehouse tables
- Reliable relationships
- Consistent KPIs
- Optimized queries
- SQL views
- Historical data
- Clearly documented business logic
- Stable data structures

## Reporting Requirements

The BI Team will use the warehouse as the primary data source for Power BI dashboards.

---

# 12. Stakeholder Requirement Summary

| Stakeholder | Primary Focus | Key Requirements |
|---|---|---|
| Executive Management | Overall Business Performance | Revenue, Orders, Growth, Customers |
| Sales Management | Sales Performance | Revenue, Products, Sellers, Trends |
| Product Management | Product Performance | Sales, Revenue, Ratings |
| Seller Management | Seller Performance | Revenue, Orders, Rankings |
| Operations Team | Order & Delivery Performance | Delivery, Orders, Status |
| Finance Team | Financial & Payment Analysis | Revenue, Payments |
| Customer Analytics | Customer Behavior | Customers, Repeat Purchases, Revenue |
| Data Analysts | Business Analysis | SQL, KPIs, Historical Data |
| BI Team | Reporting | Power BI, Views, KPIs |

---

# 13. Stakeholder-to-Data Mapping

The warehouse should provide data required by different stakeholders through common analytical dimensions and facts.

| Stakeholder | Required Data |
|---|---|
| Executive Management | Sales, Customers, Products, Sellers, Date, Geography |
| Sales Management | Sales, Products, Sellers, Date, Geography |
| Product Management | Products, Sales, Reviews, Date |
| Seller Management | Sellers, Sales, Products, Reviews |
| Operations Team | Orders, Customers, Date, Geography |
| Finance Team | Sales, Payments, Date |
| Customer Analytics | Customers, Sales, Products, Date |
| Data Analysts | All analytical datasets |
| BI Team | Dimensions, Facts, KPIs, Views |

---

# 14. Key Design Implications

The stakeholder analysis directly influences the data warehouse design.

Based on the identified requirements, the warehouse should support dimensions such as:

- Customer
- Product
- Seller
- Date
- Geography

The warehouse should also provide fact data capable of supporting:

- Sales analysis
- Order analysis
- Payment analysis
- Customer behavior analysis
- Product performance analysis
- Seller performance analysis
- Operational analysis

These requirements will be used during the Star Schema design phase.

---

# 15. Stakeholder Requirement Conclusion

The stakeholder analysis establishes the analytical needs of ShopSphere's major business and technical users.

The requirements indicate that the data warehouse must provide:

- Integrated business data
- Consistent KPIs
- Historical analysis
- Reliable analytical datasets
- Flexible SQL analysis
- Power BI-ready data
- Scalable dimensional models

These requirements will serve as the foundation for the Business Requirements and Reporting Requirements documents in the next steps of Phase 1.
