# Sales and Financial Analytics

## Overview
This project involves a hardware company that sells PCs, Mice, Printers, and peripherals. The business operates through two customer segments: **Brick & Mortar (Croma)** and **E-Commerce (Flipkart)**, managed via three channels: **Retailer**, **Distributor**, and **Direct**. The objective of this project is to assess **Sales** and **Financial Health** to support business expansion.

## Objective
The project provides actionable insights through two primary reports:
1. **Customer Performance**
2. **Market Performance vs. Target**

## Process

### ETL and Data Modeling
- Data is sourced from the following datasets: **Fact_sales_monthly**, **Dim_product**, **Dim_market**, **Dim_customer**, and a dynamically generated **dim_date** table:
  ```powerquery
  = {Number.From(#date(2018, 9, 1)) .. Number.From(#date(2024, 8, 1))}
  ```
- The transformed data is modeled using a **star schema** for efficient analysis.

### Key DAX Measures
- **Net Sales Amount**: `=SUM(fact_sales_monthly[net_sales_amount])`
- **Net Sales for 2023**: `=CALCULATE([net sales], dim_date[FY] = "2023")`
- **Net Sales Growth (2024 vs. 2023)**: `=DIVIDE([net sales 24], [net sales 23], 0)`
- **Net Sales Target (2024)**: `=SUM(ns_target_2024[ns_target])`

### Reports Delivered
1. **Customer Performance**
2. **Market Performance vs. Target**
3. **Division Report**
4. **Top & Bottom Products**
5. **New Products in 2024**
6. **Top 10 Products**
7. **Top 5 Countries**

## Finance Analytics
Additional data, such as **Fiscal Year** and **Performance Targets for 2024**, enable the creation of key financial reports:
1. **Profit & Loss (P&L) by Fiscal Year**
2. **P&L by Month & Quarter**
3. **Gross Margin (GM%) by Quarter**
4. **P&L for Markets**

## Key Insights
1. **16 New Products** are launched in 2024.
2. **Amazon** emerges as the top customer in net sales.
3. The **P&A Division** is the most in-demand for 2023 and 2024.
4. **India** performs exceptionally well in net sales.

## Conclusion
This analytical report provides actionable insights that help the company make data-driven decisions. By leveraging tools such as Power Query, star schema modeling, and DAX measures, the project highlights growth opportunities and monitors sales and financial health effectively, supporting the company’s expansion into new segments.

