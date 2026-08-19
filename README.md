# 🛒 Olist E-Commerce Power BI Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Data%20Analysis%20Expressions-2ED8B6?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

An interactive *Power BI dashboard* built on the *Olist Brazilian E-Commerce* public dataset, designed to give a business team a single view of sales performance, geography, payments, and customer satisfaction — the kind of report a marketplace ops or growth team would check weekly.

---

## 📑 Table of Contents

- [Business Problem](#-business-problem)
- [Project Overview](#-project-overview)
- [Data Preparation](#-data-preparation)
- [Data Model](#️-data-model)
- [Dashboard Pages](#-dashboard-pages)
- [Key Features](#-key-features)
- [Project Objectives](#-project-objectives)
- [Tools Used](#️-tools-used)
- [Screenshots](#-screenshots)
- [How to Use This Project](#-how-to-use-this-project)
- [Repository Structure](#-repository-structure)
- [Key Insights](#-key-insights)
- [Author](#-author)

---

## 🎯 Business Problem

Olist connects small Brazilian merchants to major marketplaces, which means the business sits at the intersection of sellers, buyers, logistics, and payments — each with its own data quirks. Leadership needs fast answers to questions that span all of them:

- Which product categories actually drive revenue, and is that changing month to month?
- Where are our customers and sellers concentrated geographically, and does that create logistics risk?
- How do customers prefer to pay, and has that shifted year over year?
- Are certain product categories quietly damaging customer satisfaction?

This dashboard pulls Olist's raw order, customer, seller, payment, and review tables into one connected model so those questions have a one-click answer instead of a spreadsheet hunt.

---

## 📊 Project Overview

This project is an interactive Power BI dashboard created to analyze Olist E-Commerce sales data. It provides insights into orders, revenue, customers, sellers, payments, products, and customer reviews across three focused report pages, each built for a different stakeholder question: how are we performing, where is it happening, and how do customers feel about it.

---

## 🔄 Data Preparation

The data was cleaned and transformed using *Power Query*, including:

- Standardizing date and currency fields across order, payment, and review tables
- Resolving duplicate and missing customer/seller location records
- Building lookup joins between order items, products, and product category translations
- Creating relationships between fact and dimension tables to support accurate analysis and interactive filtering

---

## 🏗️ Data Model

The report follows a *star-schema* approach typical of e-commerce analytics:

text
                 ┌───────────────┐
                 │  DimDate      │
                 └───────┬───────┘
                         │
┌───────────┐    ┌───────▼────────┐    ┌────────────┐
│ Customers │────│  Fact_Orders   │────│  Sellers   │
└───────────┘    └───────┬────────┘    └────────────┘
                         │
              ┌──────────┼──────────┐
              │          │          │
        ┌─────▼───┐ ┌────▼─────┐ ┌─▼──────────┐
        │ Products│ │ Payments │ │  Reviews   │
        └─────────┘ └──────────┘ └────────────┘


Orders sit at the center as the fact table, joined out to customers, sellers, products, payments, and reviews — with a shared date dimension driving all trend and year-based slicing.

---

## 📄 Dashboard Pages

### 1. Sales Overview
*KPIs:* Total Orders · Total Revenue · Average Order Value · Average Customer Rating

*Visuals:* Top 10 Product Categories · Monthly Orders Trend

*Slicers:* Year · Order Status · Product Category

This page answers "how is the business doing right now" in a single glance — revenue, order volume, order value, and satisfaction side by side, with the monthly trend line showing momentum.

### 2. Geographic Analysis
*Visuals:* Top 10 Seller Cities by Revenue · Revenue by Seller State · Orders by Customer State

*Slicers:* Year

This page maps where the money is actually made and where customers are actually buying from — useful for spotting logistics concentration risk or underserved regions.

### 3. Payments & Reviews
*Visuals:* Payment Type by Year (Matrix) · Payment Type Mix (Donut) · Average Review Score by Product Category

*Slicers:* Year

This page combines two things that are usually analyzed separately — how customers pay and how satisfied they are — so a category with both a payment-friction problem and a satisfaction problem stands out immediately.

---

## 📌 Key Features

- 🧩 Interactive *KPI Cards* for at-a-glance metrics
- 🎚️ *Slicers* for Year, Order Status, and Product Category
- 📊 *Bar and Column Charts* for category and geographic comparisons
- 📈 *Line Chart with Drill-down* for monthly order trends
- 🗺️ *Map Visualization* for customer/seller geography
- 🧮 *Matrix* for payment type by year
- 🍩 *Donut Chart* for payment type mix
- ⚙️ *Dynamic DAX Measures* driving every KPI and visual

---

## 🎯 Project Objectives

- Analyze overall sales performance
- Identify top product categories
- Track monthly orders
- Analyze customer and seller locations
- Understand payment preferences
- Measure customer satisfaction
- Create an interactive business dashboard

---

## 🛠️ Tools Used

- Microsoft Power BI
- Power Query
- DAX
- Data Modeling
- Data Visualization

---

## 📸 Screenshots

(Add screenshots to a Screenshots/ folder and reference them below)

text
Screenshots/
├── 01_Sales_Overview.png
├── 02_Geographic_Analysis.png
└── 03_Payments_Reviews.png


---

## 🚀 How to Use This Project

1. Clone the repository:
   bash
   git clone https://github.com/<your-username>/Olist-Ecommerce-PowerBI.git
   
2. Download the [Olist Brazilian E-Commerce dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) if not already included, and place the CSVs in a Dataset/ folder.
3. Open the .pbix file in *Power BI Desktop*.
4. Repoint the data sources if needed via *Transform Data → Data Source Settings*.
5. Click *Refresh* and explore all three pages using the Year, Order Status, and Product Category slicers.

---

## 📁 Repository Structure

text
Olist-Ecommerce-PowerBI/
│
├── Olist E-Commerce Dashboard.pbix
│
├── Dataset/
│   ├── olist_orders_dataset.csv
│   ├── olist_order_items_dataset.csv
│   ├── olist_customers_dataset.csv
│   ├── olist_sellers_dataset.csv
│   ├── olist_products_dataset.csv
│   ├── olist_order_payments_dataset.csv
│   ├── olist_order_reviews_dataset.csv
│   └── product_category_name_translation.csv
│
├── Screenshots/
│   ├── 01_Sales_Overview.png
│   ├── 02_Geographic_Analysis.png
│   └── 03_Payments_Reviews.png
│
└── README.md


---

## 💡 Key Insights (fill in with your actual numbers before publishing)

- Total revenue across the analyzed period was *[Value], from *[Value]** total orders
- *[Category]* is the top-performing product category by revenue
- *[State]* leads in both seller concentration and revenue share
- *[Payment Type]* is the dominant payment method, used in *__%* of orders
- *[Category]* has the lowest average review score, signaling a satisfaction gap worth investigating

---

## 👨‍💻 Author

*Hardik Kumar Kumhar*
*Skills:* Power BI | Power Query | DAX | Data Modeling | Data Visualization

---

⭐ If you find this project useful, consider giving the repository a star.
