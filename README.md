# Retail Sales Dashboard

## Overview
A full star-schema retail sales analytics dashboard built in Power BI, using the Kaggle "Product Sales Dataset (2023-2024)". This project demonstrates end-to-end dashboard development: data cleaning, dimensional modeling, DAX measure creation, and interactive report design — built independently, not from a tutorial.

## Tools Used
- Power BI (Power Query, Data Modeling, DAX)

## Process
1. **Data Cleaning**: Fixed date formatting issues (US locale MM-DD-YY), cleaned header whitespace, stripped titles/suffixes from customer names, and derived a Cost column from Revenue and Profit
2. **Star Schema Design**: Built a dimensional model with **FactSales** at the center, linked to 5 dimension tables:
   - **DimDate** — calendar table via DAX CALENDAR()
   - **DimProduct** — product hierarchy (Category, Sub-Category, Product Name)
   - **DimCustomer** — customer details with a synthetically derived Segment (High/Mid/Low Value based on spend thresholds, since the source data had no segment field)
   - **DimStore** — store/region details
   - **DimSalesperson** — salesperson assignment, since the source data had no salesperson info (built via a deterministic region-based formula)
3. **DAX Measures**: Built core measures including Total Sales, Total Profit, Total Orders, Average Order Value (AOV), Profit Margin %, Year-over-Year Growth %, and Running Total
4. **Dashboard Development**: Built a multi-visual dashboard with a KPI card row, Sales Trend line chart, Sales by Category bar chart, Sales by Region treemap, Top 10 Products and Top Customers tables, Monthly Profit Trend chart, and 5 interactive slicers (Year, Month, Salesperson, Region, Category)

## Key Features
- Fully interactive cross-filtering across all visuals via 5 slicers
- Coordinated color palette applied consistently across all charts
- Resolved a regional number-formatting issue (Indian lakhs/crores grouping vs. Western thousands grouping) via Power BI's regional settings

## Screenshots
<img width="895" height="499" alt="image" src="https://github.com/user-attachments/assets/22af953e-0ae9-4f58-a743-6b169d7c6508" />
