# Data Analysis with Google Sheets

## 📌 Project Overview
This project demonstrates a full-cycle **data analysis workflow using Google Sheets** based on a real e-commerce dataset.

The analysis focuses on:
- data cleaning and transformation,
- metric calculation,
- category normalization,
- exploratory analysis,
- dashboard-style visualization.

The project was originally developed as a diploma work and later repackaged as a standalone analytics case.

---

## 📊 Dataset
**Source:** Kaggle (public e-commerce sales dataset)

Each row represents a single order line and contains information about:
- order details,
- product,
- pricing,
- location,
- revenue and margin.

### Original Columns
- `Order Date`
- `Order ID`
- `Product`
- `Product_ean`
- `catégorie`
- `Purchase Address`
- `Quantity Ordered`
- `Price Each`
- `Cost price`
- `turnover`
- `margin`

---

## 🔄 Data Transformation

The dataset was cleaned and enriched with additional analytical fields.

### Final Columns
- `Order Date`
- `Order ID`
- `Product`
- `Product_ean`
- `category`
- `Purchase Address`
- `Quantity Ordered`
- `Price Each`
- `Cost price`
- `turnover`
- `margin`
- `Month`
- `Year`
- `Address`
- `City`
- `PostCode`
- `category`


### Key Transformations
- Extracted **Month** and **Year** from order date
- Parsed **City** and **PostCode** from address
- Normalized product categories
- Ensured numeric consistency for price, quantity, turnover, and margin

---

## 🧹 Category Normalization
Product names were mapped into higher-level categories using conditional logic.

Example Google Sheets formula:
```
=IFS(
  C3="AAA Batteries (4-pack)", "Батарейки",
  C3="AA Batteries (4-pack)", "Батарейки",
  C3="USB-C Charging Cable", "Зарядні кабелі",
  C3="Lightning Charging Cable", "Зарядні кабелі",
  C3="LG Dryer", "Побутова техніка",
  C3="LG Washing Machine", "Побутова техніка",
  C3="Wired Headphones", "Навушники",
  C3="Apple Airpods Headphones", "Навушники",
  C3="Bose SoundSport Headphones", "Навушники",
  C3="Macbook Pro Laptop", "Ноутбуки",
  C3="ThinkPad Laptop", "Ноутбуки",
  C3="iPhone", "Смартфони",
  C3="Google Phone", "Смартфони",
  C3="Vareebadd Phone", "Смартфони",
  C3="27in FHD Monitor", "Монітори",
  C3="27in 4K Gaming Monitor", "Монітори",
  C3="34in Ultrawide Monitor", "Монітори",
  C3="20in Monitor", "Монітори",
  C3="Flatscreen TV", "Смарт-ТВ",
  TRUE, "Інше"
)
```
This step allowed category-level aggregation and comparison.

## 📐 Metrics & Calculations

The following metrics were calculated using built-in Google Sheets functions.

### Aggregations
- **Total Revenue** — `SUM(turnover)`
- **Total Profit** — `SUM(margin)`
- **Total Units Sold** — `SUM(Quantity Ordered)`
- **Number of Orders** — `COUNTA(Order ID)`

### Averages
- **Average Order Value (AOV)** — `AVERAGE(turnover)`
- **Average Margin per Order** — `AVERAGE(margin)`

---

## 📈 Analysis & Visualizations

The analysis includes:
- revenue trends by month
- number of orders by month
- margin dynamics over time
- revenue breakdown by product category
- geographical distribution of sales by city

All visualizations were created directly in Google Sheets using charts and pivot tables.

---

## 🧠 Key Insights
- Sales volume and revenue show clear seasonal variation.
- A small number of product categories generate the majority of revenue.
- High-priced products contribute disproportionately to total profit.
- Order volume and revenue trends do not always move proportionally.

---

## 🛠 Tools Used
- Google Sheets
- Built-in formulas (`SUM`, `AVG`, `COUNTA`, `IFS`)
- Pivot tables
- Charts and dashboards

---

## ⚠️ Notes & Limitations
- The dataset does not include returns or refunds.
- Currency is assumed to be consistent across all records.
- The analysis focuses on descriptive insights rather than forecasting.

---

## 🔗 Project Links
- Google Sheets (view-only): `(https://docs.google.com/spreadsheets/d/1hknjSer4aKNntk3VFVSM1HtzU9Bn6ua_KXPedZ8Fvbs/edit?usp=sharing)`
- Screenshots available in the repository

---

## 👤 Author
Levytskyi Bohdan  
Junior Data Analyst
