# Data-Analysis-through-PowerBI-
An interactive Power BI dashboard developed to analyze electronic gadget sales performance across different cities, products, categories, and sales representatives. The project provides actionable business insights through data visualization, trend analysis, KPI monitoring, and performance evaluation.
# 📊 Electronic Gadget Sales Analysis Dashboard

<div align="center">

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-Data%20Source-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-Calculations-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-ETL-742774?style=for-the-badge&logo=microsoft&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-2ea44f?style=for-the-badge)

### *Transforming raw transactional data into actionable business intelligence*

> An end-to-end Power BI analytics solution covering product performance, regional sales, rep productivity, and revenue trends for an electronic gadgets business.

</div>

---

## 📌 Table of Contents

- [Project Overview](#-project-overview)
- [Business Problem](#-business-problem)
- [Dataset](#-dataset)
- [Tech Stack](#-tech-stack)
- [Dashboard Features](#-dashboard-features)
- [Key Performance Indicators](#-key-performance-indicators)
- [Analysis Performed](#-analysis-performed)
- [Business Insights](#-business-insights)
- [Project Structure](#-project-structure)
- [Future Enhancements](#-future-enhancements)
- [Author](#-author)

---

## 🧭 Project Overview

This project presents an **interactive, multi-page Power BI Sales Analytics Dashboard** built on an Electronic Gadget Sales dataset. It enables stakeholders to explore revenue patterns, product demand, regional performance, and sales team efficiency — all from a single, unified interface.

The project covers the full BI pipeline: raw data ingestion → Power Query cleaning → DAX-based KPI modeling → dashboard storytelling.

---

## 🎯 Business Problem

Sales teams and business leaders often struggle to answer critical questions quickly:

| Business Question | Solution Provided |
|---|---|
| Which products generate the most revenue? | Product-wise revenue and unit analysis |
| Which category dominates sales? | Category contribution breakdown |
| Which cities are high-demand markets? | City-level revenue heatmap and comparison |
| Who are the top-performing sales reps? | Rep performance ranking and share analysis |
| Are we growing or declining over time? | Monthly trend and growth rate tracking |

---

## 📂 Dataset

**Source File:** `electronicgadget-rev.xlsx`  
**Domain:** Retail / Consumer Electronics  
**Scope:** Multi-city, multi-product, multi-rep transactional data

### 📋 Dataset Schema

| # | Column Name | Data Type | Description |
|---|---|---|---|
| 1 | `Date1` | Date | Transaction date (used for time-series analysis) |
| 2 | `Product` | Text | Name of the electronic gadget sold |
| 3 | `Category` | Text | Product category — Laptop, Mobile Phone, Headphone |
| 4 | `Sales Rep` | Text | Name of the sales representative who closed the deal |
| 5 | `City` | Text | City where the transaction occurred |
| 6 | `No. of Units` | Integer | Quantity of units sold per transaction |
| 7 | `Price` | Decimal | Unit selling price of the product (in currency) |
| 8 | `Amount` | Decimal | Total revenue = `No. of Units × Price` |

### 🔍 Dataset Characteristics

- **Granularity:** One row = one sales transaction
- **Categories covered:** Laptops, Mobile Phones, Headphones
- **Analysis dimensions:** Time, Product, Category, Geography, Sales Rep
- **Derived metrics:** Revenue, Units Sold, Average Order Value, Sales Share %

---

## 🛠️ Tech Stack

| Tool / Technology | Role in Project |
|---|---|
| **Microsoft Power BI** | Dashboard design, report publishing, interactivity |
| **Microsoft Excel (.xlsx)** | Raw data source |
| **Power Query (M Language)** | Data ingestion, cleaning, and transformation |
| **DAX (Data Analysis Expressions)** | KPI measures, calculated columns, time intelligence |
| **Data Modeling** | Relationship building, schema design |

---

## 📈 Dashboard Features

### Dashboard 1 — Sales Overview

A high-level executive summary of overall business performance.

| Visual | Purpose |
|---|---|
| KPI Cards | Total Revenue, Total Units Sold, Avg. Revenue Per Transaction |
| Bar Chart | Top Products by Revenue |
| Pie / Donut Chart | Category-wise Revenue Contribution |
| Line Chart | Monthly Sales Trend |
| Slicers | Dynamic filters: Product, Category, City, Date Range |

---

### Dashboard 2 — Performance Analysis

A deep-dive into product, regional, and sales rep performance.

**🔹 Product Performance**
- Revenue generated per product
- Units sold per product
- Best-selling vs. low-performing products

**🔹 Category Analysis**
- Laptop vs. Mobile Phone vs. Headphone revenue split
- Category demand trend over time
- Category contribution to total units sold

**🔹 Regional Analysis**
- City-wise total revenue comparison
- City-wise volume sold
- Identification of high-growth and low-growth markets

**🔹 Sales Representative Analysis**
- Revenue generated by each rep
- Performance ranking table
- Individual rep's % share of total sales

---

## 📊 Key Performance Indicators

The dashboard monitors the following KPIs using DAX measures:

### 💰 Revenue Metrics
```
Total Revenue       = SUM(Sales[Amount])
Average Revenue     = AVERAGE(Sales[Amount])
Revenue Growth %    = (Current Period Revenue - Prior Period Revenue) / Prior Period Revenue
```

### 📦 Sales Metrics
```
Total Units Sold    = SUM(Sales[No. of Units])
Avg. Units Per Deal = DIVIDE([Total Units Sold], COUNTROWS(Sales))
```

### 👤 Sales Rep Metrics
```
Rep Revenue Share % = DIVIDE([Rep Revenue], [Total Revenue]) * 100
Top Rep             = Identified via RANKX over all reps
```

### 🌍 Regional Metrics
```
City Revenue Rank   = RANKX(ALL(Sales[City]), [Total Revenue])
Top City            = City with MAX Revenue
```

---

## 🔍 Analysis Performed

### 1. Product Performance Analysis
Evaluated each product's contribution to total revenue and demand:
- Ranked all products by revenue and units sold
- Identified hero products (high revenue + high demand)
- Flagged underperforming SKUs for strategic review

### 2. Category-Level Analysis
Compared revenue and demand across the three product categories:
- Determined which category drives the most revenue
- Assessed units sold per category for demand-side insights
- Highlighted category growth or decline using trend lines

### 3. Sales Representative Performance
Measured employee-level effectiveness:
- Calculated revenue generated and units sold per rep
- Built a performance ranking to identify top and bottom performers
- Calculated each rep's percentage share of total business revenue

### 4. City-wise / Regional Analysis
Explored geographic distribution of sales:
- Mapped revenue and volume by city
- Compared high-performing vs. low-performing markets
- Surfaced cities with untapped growth potential

### 5. Time-Series Trend Analysis
Tracked business performance over time:
- Plotted monthly sales and revenue trends
- Identified seasonal peaks and troughs
- Measured period-over-period revenue growth

---

## 🚀 Business Insights Generated

<details>
<summary><strong>📦 Product Insights</strong></summary>

- Identified highest revenue-generating products driving the majority of sales
- Quantified product demand through units-sold analysis
- Compared product performance to prioritize inventory and marketing spend

</details>

<details>
<summary><strong>🗂️ Category Insights</strong></summary>

- Determined each category's percentage contribution to total revenue
- Compared revenue per unit across categories to identify margin leaders
- Evaluated category demand trends to support product mix decisions

</details>

<details>
<summary><strong>🌍 Regional Insights</strong></summary>

- Pinpointed top-performing cities to double down on strong markets
- Identified underperforming regions with growth opportunity
- Enabled regional sales strategy decisions backed by data

</details>

<details>
<summary><strong>👥 Sales Team Insights</strong></summary>

- Ranked sales reps by revenue contribution and units sold
- Identified training needs and reward opportunities
- Enabled fair, data-backed performance reviews

</details>

---

## 📁 Project Structure

```
Electronic-Gadget-Sales-Analysis/
│
├── 📊 SALES 1 DASHBOARD.pbix          # Overview Dashboard
├── 📊 SALES 2 DASHBOARD.pbix          # Performance Analysis Dashboard
├── 📁 electronicgadget-rev.xlsx       # Raw dataset (Excel)
├── 📄 README.md                        # Project documentation
│
└── 📂 Dashboard_Screenshots/
    ├── Dashboard1.png                  # Sales Overview screenshot
    └── Dashboard2.png                  # Performance Analysis screenshot
```

---

## 🔮 Future Enhancements

| Enhancement | Description |
|---|---|
| 🤖 **Sales Forecasting** | Predict future revenue using time-series ML models (Prophet / ARIMA) |
| 👥 **Customer Segmentation** | Group buyers by purchasing behavior using clustering (K-Means) |
| 💹 **Profitability Analysis** | Add cost data to track margins alongside revenue |
| 📦 **Inventory Optimization** | Predict stock requirements to prevent shortages or overstock |
| 🔴 **Real-Time Reporting** | Connect Power BI to a live database for streaming dashboards |

---

## 📷 Dashboard Screenshots

### Dashboard 1 — Sales Overview
> *Screenshot coming soon — add to `/Dashboard_Screenshots/Dashboard1.png`*

### Dashboard 2 — Performance Analysis
> *Screenshot coming soon — add to `/Dashboard_Screenshots/Dashboard2.png`*

---

## 👩‍💻 Author

<div align="center">

### Gugi
**Final Year B.Tech — Artificial Intelligence & Data Science**

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)]()
[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)]()
[![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white)]()
[![Excel](https://img.shields.io/badge/Excel-217346?style=flat-square&logo=microsoft-excel&logoColor=white)]()
[![Machine Learning](https://img.shields.io/badge/Machine%20Learning-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)]()

</div>

---

<div align="center">

⭐ **If this project was helpful, please consider starring the repository!**

*Data-driven decisions begin with meaningful insights.*

</div>
