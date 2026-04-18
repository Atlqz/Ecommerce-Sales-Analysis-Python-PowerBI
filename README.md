# Ecommerce-Sales-Analysis-Python-PowerBI
Exploratory data analysis and interactive dashboard for Superstore e-commerce sales. Python (Pandas, Matplotlib) + Power BI.

# E-Commerce Sales Analysis | Excel · Python · Power BI

![Python](https://img.shields.io/badge/Python-3.11-blue?style=flat-square&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat-square&logo=pandas)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=flat-square&logo=powerbi)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat-square)

## Project Overview

End-to-end analysis of **9,994 transactions** from a Superstore-style e-commerce retailer, covering sales across four US regions, three customer segments, and three product categories from 2015 to 2018.

The business question driving the analysis: **where is revenue concentrated, and what operational patterns explain the gaps between regions and segments?**

The pipeline runs from raw data in Excel through Python for cleaning and EDA, to an interactive Power BI dashboard for stakeholder reporting.

---

## Key Findings

### Revenue concentration
- **Technology generated $827,062** in total sales, leading all categories by over $100K despite having the fewest individual orders, meaning higher average order value drives its performance, not volume.
- The **Canon imageCLASS 2200 Copier alone contributed $61,600**, more than the bottom 200 products combined, a classic long-tail distribution that has real implications for inventory prioritisation.

### Regional performance gap
- The **West region accounted for 31.4% of total revenue ($710,117)**, nearly double the South ($388,437) despite similar population coverage, suggesting either a stronger customer base or more effective regional operations.
- The **South's underperformance is not explained by product mix**, it underperforms across all three categories, pointing to a distribution or market penetration issue rather than a category-specific one.

### Customer segments
- The **Consumer segment drove 50.6% of revenue**, but the **Corporate segment had a higher average order value**, meaning corporate customers buy less often but spend more per order, which has different implications for acquisition vs. retention strategy.
- **Home Office (16.9% of revenue)** is the smallest segment but showed the steadiest month-on-month growth across the dataset period.

### Seasonality and operations
- **November and December consistently peak**, with November 2017 being the single highest revenue month in the dataset, holiday demand is the dominant seasonal driver.
- **Standard Class shipping (5.0 days average)** was used in 59.7% of orders despite Same Day and First Class options being available, suggesting customers are price-sensitive on delivery rather than speed-sensitive.
- There were **11 orders where shipping took longer than 7 days on Standard Class**, flagging potential fulfilment outliers worth investigating for customer satisfaction impact.

---

## Pipeline

```
Raw CSV
  └── Excel        , table formatting, duplicate removal, date standardisation,
                      null checks, added Month and Year columns
       └── Python  , EDA, aggregations, feature engineering, visualisations
            └── Power BI, interactive dashboard for stakeholder reporting
```

---

## Python Analysis

Libraries used: `pandas`, `matplotlib`, `seaborn`

Key operations performed:
- Calculated total and average sales by category, region, segment, and month
- Engineered a `Shipping Days` column (`Ship Date − Order Date`) to analyse fulfilment performance
- Identified seasonal patterns through monthly revenue trend analysis
- Produced 7 charts covering category performance, regional breakdown, segment split, monthly trend, and shipping delay distribution

---

## Power BI Dashboard

The dashboard is structured around two business questions:

1. **Where is revenue coming from?**, KPI cards for total sales, top category, top region; bar charts by category and region
2. **Who is buying?**, Segment breakdown by revenue share and order count

Interactive region slicer filters all visuals simultaneously.

<img width="1283" height="716" alt="image" src="https://github.com/user-attachments/assets/2e5c8a24-78ff-49de-8924-b36de756e472" />


---

## Repository Structure

```
ecommerce-sales-analysis/
│
├── raw_superstore.csv               # Original dataset
├── superstore_cleaned_final.csv     # Post-Excel cleaning, used in Python and Power BI
│
├── supersore_sales_snalysis.ipynb    # Full EDA with annotated markdown cells
│
├── superstore_sales_report.pbix      # Power BI dashboard export
│
└── README.md
```

---

## What I Would Do Next

- **Profitability analysis**: The dataset includes a `Profit` column not analysed here. Overlaying profit margin onto the revenue findings would likely reveal that some high-revenue products (e.g. the copier) have thin margins, changing the prioritisation story entirely.
- **Churn and repeat purchase analysis**: Identify which customers bought once vs. multiple times, and whether segment or region predicts repeat behaviour.
- **Predictive model**: Build a simple time-series forecast (Facebook Prophet or ARIMA) on monthly sales to project the next two quarters, turning this descriptive analysis into something actionable for planning.
