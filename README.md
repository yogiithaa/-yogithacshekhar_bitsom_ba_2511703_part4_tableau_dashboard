# Retail Executive Performance Dashboard

## Business Problem Summary

The retail leadership team requires an executive dashboard to monitor overall business performance across sales, profitability, customer behavior, regional performance, shipping efficiency, and return patterns.

The objective of this project is to provide leadership with a single dashboard that supports strategic decision-making by identifying growth opportunities, operational risks, and performance trends across the organization.

---

## Dataset Description

The dataset contains retail transaction data covering sales, profit, customers, products, shipping, marketing channels, and returns.

### Dataset Overview

* Total Records: 4,200
* Date Fields:

  * Order Date
  * Ship Date
* Geographic Fields:

  * Region
  * State
  * City
* Customer Fields:

  * Customer ID
  * Customer Segment
* Product Fields:

  * Category
  * Sub Category
  * Product Name
* Performance Metrics:

  * Sales
  * Profit
  * Quantity
  * Discount
  * Delivery Days
  * Customer Rating
* Operational Fields:

  * Ship Mode
  * Return Flag
  * Campaign Channel

The dataset was used to build multiple analytical views and an executive dashboard in Tableau.

---

## Tableau Workbook Description

Workbook File:

tableau/executive_dashboard.twbx

The Tableau workbook contains:

* KPI Summary Cards
* Sales Trend Analysis
* Regional Performance Analysis
* Category Profitability Analysis
* Customer Segment Analysis
* Shipping Performance Analysis
* Return Analysis
* Interactive Dashboard Filters
* Dashboard Action Interactions

The workbook is designed for executive-level monitoring and business decision support.

---

## Calculated Fields Created

### Profit Margin

Profit divided by Sales.

```text
SUM([Profit]) / SUM([Sales])
```

### Cost

Estimated product cost.

```text
SUM([Sales]) - SUM([Profit])
```

### Average Order Value

Average sales per order.

```text
SUM([Sales]) / COUNTD([Order Id])
```

### Return Rate

Returned orders divided by total orders.

```text
SUM([Return Flag]) / COUNTD([Order Id])
```

### Shipping Delay Bucket

Categorizes delivery performance.

```text
Fast: <= 2 Days
Normal: 3–5 Days
Delayed: > 5 Days
```

### Additional Fields

* Returned Orders
* Discount Bucket

---

## Dashboard Components

### KPI Cards

* Total Sales
* Total Profit
* Profit Margin
* Return Rate

### Analytical Views

#### Sales Trend View

Displays monthly sales trends across regions.

#### Regional Performance View

Compares sales and profit across regions.

#### Category Profitability View

Ranks categories and sub-categories by profitability.

#### Customer Segment Performance View

Compares customer segments by sales performance.

#### Shipping Performance View

Analyzes delivery efficiency by shipping mode.

#### Return Analysis View

Examines return behavior and return-related business risk.

---

## Filters and Interactions Used

### Dashboard Filters

* Region
* Category
* Customer Segment
* Ship Mode
* Order Date
* Campaign Channel

### Dashboard Interaction

A dashboard filter action was created using the Regional Performance chart.

Selecting a region dynamically filters all other visualizations, allowing users to perform focused regional analysis.

---

## Key Business Insights

1. Sales performance fluctuates throughout the reporting period.
2. South region generates the highest sales and profit.
3. Technology products are the strongest contributors to profitability.
4. Furniture products generate comparatively lower profit.
5. Home Office and Consumer segments contribute the highest sales.
6. Delivery performance varies significantly across shipping methods.
7. Return rate is 4.55%, indicating opportunities to reduce operational losses.
8. Overall profit margin remains healthy at 15.35%.
9. Technology products present significant growth opportunities.
10. Regional performance differences highlight expansion opportunities.

Detailed insights are documented in:

outputs/business_insights.md

---

## Dashboard Story Summary

The dashboard reveals strong overall business performance driven primarily by technology products and high-performing regions such as South.

While profitability remains healthy, opportunities exist to improve logistics performance, reduce return rates, and strengthen lower-performing product categories and regions.

The dashboard helps leadership quickly identify both growth opportunities and operational risks using a combination of KPI monitoring and interactive analysis.

Detailed narrative analysis is available in:

outputs/dashboard_story.md

---

## Assumptions and Limitations

### Assumptions

* Return Flag = 1 indicates a returned order.
* Delivery Days accurately represent shipment duration.
* Order ID uniquely identifies each order.
* Sales and Profit values are correctly recorded in the source data.
* All transactions are valid retail sales records.

### Limitations

* Historical data only.
* No customer demographic data available.
* No competitor information included.
* No external economic or seasonal factors included.
* Dashboard findings should be combined with additional business context before strategic decisions are made.

---

## Screenshots Included

Located in:

screenshots/

### Included Files

* full_dashboard.png
* sales_trend_view.png
* regional_performance_view.png
* category_profitability_view.png
* filter_interaction_view.png

These screenshots provide evidence of dashboard construction, analytical views, and interactive functionality.

---

## Repository Structure

```text
part4_tableau_dashboard/
├── data/
│   └── dashboard_sales_data.xlsx
├── tableau/
│   └── executive_dashboard.twbx
├── outputs/
│   ├── dashboard_story.md
│   ├── business_insights.md
│   └── chart_selection_justification.md
├── screenshots/
│   ├── full_dashboard.png
│   ├── sales_trend_view.png
│   ├── regional_performance_view.png
│   ├── category_profitability_view.png
│   └── filter_interaction_view.png
└── README.md
```

## Project Outcome

The completed Tableau dashboard provides leadership with a centralized, interactive view of retail business performance, enabling data-driven decision-making across sales, profitability, operations, customer segments, and risk management.
