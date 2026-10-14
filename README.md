# E-Commerce Sales & Customer Analytics

An end-to-end data analytics project using **MySQL and Power BI** to analyze e-commerce sales, customer behavior, product performance, and business trends. The project combines SQL-based analysis, interactive dashboards, customer segmentation, and automated monthly reporting to transform raw data into actionable business insights.

## Project Overview

This project demonstrates an end-to-end analytics workflow, from querying relational datasets in MySQL to building interactive Power BI dashboards.

The analysis focuses on sales performance, customer purchasing behavior, product category performance, order trends, and key business metrics. It also includes a folder-based monthly reporting workflow that simplifies the process of updating reports when new CSV files become available.

## Business Objectives

- Analyze overall revenue, order volume, customer count, and average order value.
- Identify monthly sales trends and revenue fluctuations.
- Determine the highest-performing product categories and products.
- Identify top customers based on spending.
- Analyze customer purchasing frequency and spending behavior.
- Compare customer segments and age groups.
- Examine order status, payment methods, and geographical sales patterns.
- Validate Power BI metrics against SQL query results.
- Simplify monthly reporting using Power Query transformations.

## Tools & Technologies

| Tool | Purpose |
|---|---|
| MySQL | SQL queries and business analysis |
| Power BI | Interactive dashboards and KPI reporting |
| Power Query | Data cleaning and transformation |
| DAX | Measures, calculated columns, and customer segmentation |
| GitHub | Version control and project documentation |

## Dataset Structure

The relational dataset contains five main tables.

| Table | Description |
|---|---|
| `customers` | Customer details and demographic information |
| `products` | Product names, categories, subcategories, and prices |
| `orders` | Order dates, customer references, status, and shipping details |
| `order_items` | Products, quantities, and unit prices associated with orders |
| `payments` | Payment methods, payment status, dates, and amounts |

A dedicated date dimension was created in Power BI to support time-based analysis.

## Data Model

The Power BI data model connects the main tables through the following relationships:

- Customers → Orders
- Orders → Order Items
- Products → Order Items
- Orders → Payments
- DimDate → Orders

This model supports analysis across customers, products, orders, payments, revenue, and time.

## Key Performance Indicators (KPIs)

The following metrics were calculated from the dataset.

| KPI | Result |
|---|---:|
| Total Revenue | ₹21.99M |
| Total Orders | 250 |
| Total Customers | 100 |
| Average Order Value | ₹87.97K |

*Note: These figures represent the results reported by the project. Revenue and average order value are displayed in rounded units in the dashboard.*

## SQL Analysis

The project includes **30 business-focused SQL queries** covering basic, intermediate, and advanced SQL concepts.

### SQL Concepts Used

- INNER JOIN and LEFT JOIN
- GROUP BY and HAVING
- Aggregate functions
- CASE statements
- Subqueries
- Common Table Expressions (CTEs)
- Window functions
- RANK() and PARTITION BY
- LAG()
- Cumulative calculations
- Month-over-month analysis

### Business Questions Answered

The SQL analysis explores questions such as:

1. Who are the top 10 customers by spending?
2. Which product categories generate the most revenue?
3. Which products perform best based on sales?
4. Which customers have never placed an order?
5. Which customers spend more than the average customer?
6. Which product generates the highest revenue in each category?
7. How does revenue vary across shipping states?
8. What percentage of orders are cancelled?
9. Which payment methods contribute the most revenue?
10. How does monthly revenue change over time?
11. What is the month-over-month revenue growth?
12. How does cumulative revenue develop over the analysis period?

The complete SQL analysis is available in:

`SQL/Ecommerce_SQL_Analysis.sql`

## Power BI Dashboard

The interactive Power BI dashboard contains two pages.

### Page 1: Sales Overview

This page provides a high-level view of sales performance.

**Key components:**
- Total Revenue
- Total Orders
- Total Customers
- Average Order Value
- Monthly Revenue Trend
- Revenue by Product Category
- Orders by Status
- Revenue by State
- Interactive filters

![Sales Overview Dashboard](Screenshots/Sales_Overview.png)

### Page 2: Customer & Segmentation Analysis

This page focuses on customer behavior, spending patterns, and purchasing frequency.

**Key components:**
- Repeat Customers
- New Customers
- Average Customer Spend
- Customer Segmentation
- Top 10 Customers by Spending
- Customer Distribution by Age Group
- Customer Spending by Age Group
- Gender and State Filters

![Customer Segmentation Dashboard](Screenshots/Customer_Segmentation.png)

## Customer Segmentation

Customers were classified according to their number of orders.

| Segment | Definition |
|---|---|
| Premium | 5 or more orders |
| Regular | 2–4 orders |
| Occasional | 1 order |

The analysis indicates that Regular customers form the largest customer segment, followed by Occasional and Premium customers.

This segmentation helps compare purchasing frequency and understand differences in customer behavior.

## Key Business Insights

The analysis produced the following findings:

- **Revenue concentration:** Electronics generated approximately ₹19.36M, representing the majority of reported revenue.
- **Overall performance:** The dataset contains approximately ₹21.99M in reported revenue across 250 orders.
- **Average order value:** The reported average order value is approximately ₹87.97K.
- **High-value customers:** Rakesh Banerjee was identified as the highest-spending customer, with spending of approximately ₹8.96L, followed by Ankit Kumar.
- **Age-group analysis:** The 20–30 and 31–45 age groups each contain 32 customers, but the 20–30 group contributes substantially higher customer spending.
- **Customer behavior:** A higher order frequency does not always mean higher total spending. Some customers with fewer orders contribute more revenue than customers with more frequent purchases.
- **Sales trends:** Monthly revenue fluctuates throughout the analysis period, highlighting the importance of monitoring sales performance over time.

These findings can help businesses understand revenue concentration, customer value, product performance, and changes in sales trends.

## Data Validation

Key Power BI calculations were compared against MySQL query results to check consistency between the database analysis and dashboard.

### Validation Results

| Metric | MySQL Result | Power BI Display |
|---|---:|---:|
| Total Revenue | ₹21,993,308.30 | ₹22M |
| Average Order Value | ₹87,973.23 | ₹88K |

The differences shown above are due to rounding in the dashboard display.

The validation process also covered:

- Total Orders
- Total Customers
- Top 10 Customers by Spending
- Revenue by Product Category
- Monthly Revenue Trend

## Automated Monthly Sales Reporting

The project includes a folder-based monthly reporting workflow using Power BI and Power Query.

The workflow allows new monthly CSV files to be incorporated into the report without manually rebuilding the transformation steps for each file.

### Key Features

- Combines multiple monthly CSV files using the Power BI Folder connector.
- Applies reusable Power Query transformations to incoming files.
- Cleans text values and standardizes data types.
- Removes duplicate order-item records.
- Tracks files loaded and rows loaded.
- Monitors orders, customers, sales revenue, and average order value.
- Supports file-level validation and monthly performance analysis.
- Updates KPIs, validation tables, and charts after a report refresh.

### Automation Workflow

1. Export the latest monthly sales data as a CSV file using the required column structure.
2. Place the CSV file in the designated monthly sales folder.
3. Refresh the Power BI report.
4. Power Query combines the available files and applies the configured transformations.
5. KPIs, validation tables, and monthly charts update based on the refreshed data.

The workflow was tested by adding an April 2024 CSV file and refreshing the report.

**Important:** This implementation demonstrates folder-based refresh automation in Power BI Desktop. Power BI Service scheduled refresh is not currently configured.

## Skills Demonstrated

### SQL
- Joins and aggregations
- Subqueries and CTEs
- CASE statements
- Window functions and ranking
- Time-series analysis
- Business-focused query development

### Power BI
- Data modeling and relationships
- Power Query transformations
- DAX measures and calculated columns
- KPI development
- Interactive dashboards and slicers
- Customer segmentation
- Data visualization

### Data Analytics
- Data preparation and validation
- Sales and revenue analysis
- Customer behavior analysis
- Product performance analysis
- Trend analysis
- Business insight generation
- Reporting automation

## Repository Structure

```text
Ecommerce-Sales-Customer-Analytics/
│
├── Dataset/
│
├── PowerBI/
│   └── Ecommerce_Analytics_Dashboard.pbix
│
├── Screenshots/
│   ├── Sales_Overview.png
│   └── Customer_Segmentation.png
│
├── SQL/
│   └── Ecommerce_SQL_Analysis.sql
│
└── README.md
```

## Project Summary

This project demonstrates practical experience in **SQL-based business analysis, Power BI dashboard development, customer segmentation, data validation, and monthly reporting automation**.

By combining relational data analysis with interactive visualizations, the project transforms e-commerce data into business-focused insights that support sales monitoring and customer analysis.

The project was developed as a portfolio project to demonstrate skills relevant to entry-level Data Analyst and Business Intelligence Analyst roles.