# Sales & Customer Performance Dashboard | Tableau

Interactive Tableau dashboards built to help sales managers and executives analyze year over year sales performance and understand customer behavior, built from a user story style requirements brief for a Sales Performance analytics initiative.

**Live Dashboard:** https://public.tableau.com/views/SalesandCustomerdataAnalysis/CustomerDashBoard?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

## Overview

This project delivers two linked dashboards from a single retail sales dataset (Superstore style data, ~9,994 orders spanning 2020 to 2023, 793 unique customers):

1. **Sales Dashboard** — sales, profit, and quantity trends with year over year comparison
2. **Customer Dashboard** — customer counts, order behavior, and top customer profitability

Both dashboards are built off the same data model and share a global year selector and cross filtering, so users can drill from either view into product category, sub category, region, state, or city.

## Business Requirements

Sourced from the project's user story brief:

**Sales Dashboard**
- KPI overview of total sales, profit, and quantity, current year vs. previous year
- Monthly trend lines for each KPI, with highest and lowest months flagged
- Product sub category comparison: current year vs. prior year sales, plus a profit view
- Weekly sales and profit trends against a rolling average, highlighting above/below average weeks

**Customer Dashboard**
- KPI overview of total customers, sales per customer, and total orders, current year vs. previous year
- Monthly trend lines for each KPI, with highest and lowest months flagged
- Customer distribution by number of orders placed (loyalty/engagement view)
- Top 10 customers by profit, with rank, order count, sales, profit, and last order date

**Interactivity**
- Dynamic year selector for exploring historical data
- Easy navigation between the two dashboards
- Cross filtering: clicking any chart filters the rest of the dashboard
- Global filters for category, sub category, region, state, and city

## Data Model

Four source tables, joined on Customer ID, Product ID, and Postal Code:

| Table | Rows | Key Fields |
|---|---|---|
| `Orders.csv` | 9,994 | Order ID, Order/Ship Date, Ship Mode, Segment, Sales, Quantity, Discount, Profit |
| `Customers.csv` | 793 | Customer ID, Customer Name |
| `Products.csv` | 1,894 | Product ID, Category, Sub-Category, Product Name |
| `Location.csv` | 632 | Postal Code, City, State, Region, Country |

## Key Calculated Fields

- **CY / PY metrics** — parameter driven current year and previous year measures for Sales, Profit, Quantity, Customers, Orders, and Sales per Customer, each with a matching `% Diff` calculation
- **Select Year (parameter)** — drives which year is treated as "current" across both dashboards
- **Min/Max flags** — per KPI, identifies the highest and lowest performing month for the highlighted markers on each trend line
- **Nr of Orders per Customers** — powers the customer distribution histogram
- **KPI Sales Avg / KPI Profit Avg** — rolling weekly averages used in the Weekly Trends view
- **Action parameters** — support click to filter interactivity across Sub-Category, Customer Name, Week, and Orders per Customer

## Key Insights (2023 vs. 2022)

- Total Sales: **$733K** (+20.36% YoY)
- Total Profit: **$93K** (+14.24% YoY)
- Total Quantity Sold: **12K units** (+14.24% YoY)
- Total Customers: **693** (+8.62% YoY)
- Total Orders: **693** (+28.29% YoY)
- Average Sales per Customer: **$1,058** (+10.80% YoY)
- Top customer by profit: Raymond Buch ($6,781 profit, $14,203 sales)

## Tools Used

- **Tableau Public Desktop** — dashboard design and calculated fields
- **Data source:** 4 relational CSV files (Orders, Customers, Products, Location)

## Files in This Repo

- `Sales & Customer Dashboards (Dynamic).twbx` — packaged Tableau workbook
- `/data` — source CSV files
- `/screenshots` — exported dashboard images
- `Project_Requirements.docx` — original user story / requirements brief

## Author

**Mohit Rautela**
[LinkedIn](https://linkedin.com/in/mohitrautela11) · [Tableau Public Profile](https://public.tableau.com/app/profile/mohit.rautela)
