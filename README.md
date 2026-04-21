 # 🛒 Apocalypse Store Sales Dashboard

A Power BI dashboard analysing the sales performance of a survival gear store across 4 customers, 10 products, and 74 orders.

---

## 📊 Dashboard Overview

![Dashboard Screenshot](screenshots/dashboard_overview.png)

The dashboard provides an interactive view of revenue, profitability, and sales trends — with slicers allowing filtering by customer and product.

---

## 🔍 Key Insights

- **Total Revenue:** $87,945.09
- **Gross Profit:** $43,212.43
- **Profit Margin:** 49.1%
- **Total Orders:** 74
- **Average Units Per Order:** 40.6

### 🏆 Top Performing Product
**Weatherproof Jacket** generated the most revenue at **$21,197.35**, while the **Multitool Survival Knife** was the best seller by units with **477 units sold**.

### 👥 Top Customer
**Apocalypse Preppers United** was the highest revenue customer at **$31,947.11**, while **Uncle Joe's Prep Shop** led in units sold with **951 units**.

### 📦 Revenue by Product
| Product | Revenue |
|---|---|
| Weatherproof Jacket | $21,197.35 |
| Stainless Steel Axe | $15,925.00 |
| Multitool Survival Knife | $13,828.23 |
| Nylon Rope | $12,086.10 |
| Backpack | $8,477.88 |
| Water Purifier | $6,866.75 |
| Solar Battery Flashlight | $4,821.18 |
| Duct Tape | $2,281.25 |
| Waterproof Matches | $1,518.10 |
| N95 Mask | $943.25 |

### 👥 Units Sold by Customer
| Customer | Units Sold |
|---|---|
| Uncle Joe's Prep Shop | 951 (30.29%) |
| Apocalypse Preppers United | 828 (26.39%) |
| Alex The Analyst Apocalypse Preppers | 613 (19.53%) |
| Prep4Anything Prepping Store | 609 (19.41%) |

---

## 🛠️ Skills Demonstrated

- **Data Modelling** — Built a relationship between the Products and Sales tables using Product ID
- **DAX Measures** — Created calculated measures including Total Revenue, Gross Profit, Profit Margin %, Total Units Sold, Avg Units Per Order, and Best Selling Product
- **Power Query** — Cleaned and transformed raw data including fixing date formats
- **Interactive Dashboard** — Built slicers for Customer and Product Name that filter all visuals simultaneously
- **Data Visualisation** — Designed bar charts, pie charts, line charts, and KPI cards

---

## 📐 DAX Measures Used

```dax
Total Revenue = 
    SUMX('Apocolypse Sales', 
    'Apocolypse Sales'[Units Sold] * RELATED('Apocolypse Store'[Price]))

Total Cost = 
    SUMX('Apocolypse Sales', 
    'Apocolypse Sales'[Units Sold] * RELATED('Apocolypse Store'[Production Cost]))

Gross Profit = [Total Revenue] - [Total Cost]

Profit Margin % = DIVIDE([Gross Profit], [Total Revenue], 0)

Total Units Sold = SUM('Apocolypse Sales'[Units Sold])

Avg Units Per Order = AVERAGE('Apocolypse Sales'[Units Sold])

Best Selling Product = 
MAXX(
    TOPN(1, VALUES('Apocolypse Store'[Product Name]), [Total Units Sold], DESC),
    'Apocolypse Store'[Product Name]
)
```

---

## 🗂️ Data Source

| Sheet | Description |
|---|---|
| Apocolypse Store | Product catalogue with 10 products, prices, and production costs |
| Apocolypse Sales | 74 sales transactions with customer, product, units sold, and date |

---

## 🧰 Tools Used

- **Power BI Desktop** — Dashboard building and DAX
- **Microsoft Excel** — Source data
- **DAX** — Data Analysis Expressions for calculated measures
- **Power Query** — Data cleaning and transformation

---

## 🚀 How to View This Project

1. Download the `.pbix` file from this repository
2. Open it in **Power BI Desktop** (free download at microsoft.com/powerbi)
3. Use the **Customer** and **Product Name** slicers to explore the data interactively

---

*Built as part of a self-directed Power BI learning journey.*

