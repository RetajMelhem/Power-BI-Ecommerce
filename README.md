# E-Commerce Analytics Dashboard

This project is a Power BI dashboard built using the Brazilian E-Commerce Dataset (Olist Dataset).
The goal of the project is to analyze sales performance, product behavior, and delivery efficiency using interactive dashboards and visual analytics.

The dashboard was designed with a modern dark UI style and focuses on presenting business insights in a simple and clear way.

---

# Dashboard Pages

## 1. Executive Overview

This page gives a general overview of the business performance.

Main KPIs:

* Total Revenue
* Total Orders
* Average Order Value
* Total Products Sold
* Average Freight Cost
* Delivery Success Rate

Visuals:

* Revenue Trend
* Revenue by Month
* Order Status Distribution
* Top Categories by Revenue
* Top Sellers by Revenue

---

## 2. Product Analytics

This page focuses on product performance and category analysis.

Main KPIs:

* Total Products
* Total Orders
* Total Revenue
* Average Product Price
* Top Category
* Revenue Growth

Visuals:

* Top Categories Ordered
* Top Categories by Revenue
* Average Price by Category
* Top Categories by Freight Cost

---

## 3. Delivery & Shipping Performance

This page analyzes delivery speed and shipping efficiency.

Main KPIs:

* Average Delivery Days
* Average Approval Days
* On-Time Delivery %
* Late Delivery %
* Average Delay Days

Visuals:

* Gauge Chart for On-Time Delivery
* Average Delivery Days by Category
* Late Orders Trend
* Decomposition Tree for Delay Analysis

---

# Dataset Tables Used

The project mainly uses:

* Orders Dataset
* Order Items Dataset
* Products Dataset

Relationships were created between the tables using:

* order_id
* product_id

---

# Calculated Columns & Measures

Some DAX calculations used in the project:

## Delivery Days

```DAX
Delivery Days =
DATEDIFF(
    Orders[order_purchase_timestamp],
    Orders[order_delivered_customer_date],
    DAY
)
```

## Delay Days

```DAX
Delay Days =
DATEDIFF(
    Orders[order_estimated_delivery_date],
    Orders[order_delivered_customer_date],
    DAY
)
```

## Delivery Status

```DAX
Delivery Status =
IF(
    Orders[order_delivered_customer_date]
        <= Orders[order_estimated_delivery_date],
    "On Time",
    "Late"
)
```

---

# Tools & Technologies

* Power BI
* DAX
* Power Query
* Data Modeling

---

# Project Goal

The main purpose of this project is to:

* Practice data analysis using Power BI
* Build interactive dashboards
* Analyze sales and logistics performance
* Improve data visualization and dashboard design skills

