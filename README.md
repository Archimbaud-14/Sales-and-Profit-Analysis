# 📊 Sales and Profit Analysis Across Regions and Categories

> Structured EDA to uncover revenue drivers, identify underperforming segments, and deliver actionable profit improvement strategies.

![Python](https://img.shields.io/badge/Python-3.13-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.3-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.10-11557C)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-4C72B0)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Level](https://img.shields.io/badge/Level-Intermediate-orange)

---

## 📋 Table of Contents

- [About the Project](#-about-the-project)
- [Dataset Overview](#-dataset-overview)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Analysis Workflow](#-analysis-workflow)
- [Key Findings](#-key-findings)
- [Visualizations](#-visualizations)
- [Business Insights](#-business-insights)
- [Bonus Features](#-bonus-features)

---

## 📖 About the Project

This project analyzes **9,994 retail transactions** from a US superstore spanning **2014–2017** across 4 regions and 17 sub-categories. The goal is to identify which regions, categories and sub-categories drive revenue and profit, detect loss-making segments, and uncover the impact of discounting on profitability.

### Objectives
- Multi-level aggregation by Region, Category, and Sub-Category
- Detect sub-categories with **negative total profit**
- Analyze the **Discount–Profit relationship**
- Track **yearly sales growth** (2014 → 2017)
- Deliver **4 actionable business insights** for profit improvement

---

## 📊 Dataset Overview

| Property | Detail |
|----------|--------|
| **Source** | [Kaggle — Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final) |
| **File** | `Sample - Superstore.csv` |
| **Records** | 9,994 orders |
| **Columns** | 21 features |
| **Date Range** | January 2014 – December 2017 |
| **Regions** | West, East, Central, South |
| **Categories** | Technology, Office Supplies, Furniture |
| **Missing Values** | None |

### Key Columns

| Column | Description |
|--------|-------------|
| `Order Date` / `Ship Date` | Transaction and shipment dates |
| `Region` | US geographic region |
| `Category` / `Sub-Category` | Product classification |
| `Sales` | Order revenue ($) |
| `Profit` | Order profit/loss ($) |
| `Discount` | Applied discount rate (0–0.8) |
| `Quantity` | Items ordered |

---

## 📁 Project Structure

```
Sales and Profit Analysis Across Regions and Categories/
│
├── 📓 Sales_Profit_Analysis.ipynb          # Main Jupyter notebook
├── 📝 note.md                              # Methodology & findings
├── 📄 README.md                            # Project documentation
├── 📊 Sample - Superstore.csv              # Raw dataset
│
├── 🖼️ chart1_profit_by_subcategory.png     # Bar: Profit by Sub-Category
├── 🖼️ chart2_discount_vs_profit.png        # Scatter: Discount vs Profit
├── 🖼️ chart3_yearly_sales_trend.png        # Bar+Line: Yearly trend
├── 🖼️ chart4_region_sales_profit.png       # Dual bar: Region performance
├── 🖼️ chart5_profit_margin_category.png    # ⭐ Color-coded margin bar
└── 🖼️ chart6_heatmap_region_category.png   # ⭐ Heatmap: Region × Category
```

---

## 🚀 Getting Started

```bash
cd "Sales and Profit Analysis Across Regions and Categories"
pip install pandas matplotlib seaborn jupyter
jupyter notebook Sales_Profit_Analysis.ipynb
```

---

## 🔄 Analysis Workflow

```
┌──────────────────┐    ┌──────────────────┐    ┌──────────────────┐
│  1. Data Load     │───▶│  2. Quality       │───▶│  3. Preprocess    │
│  9,994 orders     │    │  Check            │    │  Dates & Shipping │
└──────────────────┘    └──────────────────┘    └──────────────────┘
         │
         ▼
┌──────────────────┐    ┌──────────────────┐    ┌──────────────────┐
│  4. Multi-Level   │───▶│  5. Negative      │───▶│  6. Discount vs   │
│  Aggregation      │    │  Profit Detection │    │  Profit Analysis  │
└──────────────────┘    └──────────────────┘    └──────────────────┘
         │
         ▼
┌──────────────────┐    ┌──────────────────┐    ┌──────────────────┐
│  7. Yearly Trend  │───▶│  8. Visualize     │───▶│  9. Business      │
│  (2014–2017)      │    │  (6 Charts)       │    │  Insights (4)     │
└──────────────────┘    └──────────────────┘    └──────────────────┘
```

---

## 🔍 Key Findings

| Metric | Value |
|--------|-------|
| 💰 **Total Sales** | ~$2.3M |
| 📈 **Total Profit** | ~$286K |
| 📊 **Overall Margin** | ~12.5% |
| 🏆 **Top Region (Sales)** | West ($725K) |
| 💎 **Top Category (Profit)** | Technology ($145K, ~17% margin) |
| ❌ **Loss-Making Sub-Cat** | Tables (-$17K) |
| 📅 **Peak Year** | 2017 ($733K sales) |
| ⚠️ **Discount Danger Zone** | >40% = almost guaranteed loss |

---

## 📈 Visualizations

### Chart 1 — Profit by Sub-Category (Negatives in Red)
> Horizontal bar ranking all 17 sub-categories. Loss-making items (Tables, Bookcases, Supplies) highlighted in red. Copiers leads with ~$56K profit.

### Chart 2 — Discount vs Profit (Scatter Plot)
> Shows strong negative correlation between discount and profit. Orders above 40% discount cluster heavily in the loss zone.

### Chart 3 — Yearly Sales & Profit Trend
> Dual-axis chart showing consistent ~20% YoY sales growth. 2017 is the peak year at $733K.

### Chart 4 — Regional Sales & Profit
> Side-by-side comparison showing West leads sales but profit margins vary across regions.

### Chart 5 — ⭐ Profit Margin by Category (Color-Coded)
> Traffic-light coloring: Technology (green, ~17%), Office Supplies (orange), Furniture (red, ~2%).

### Chart 6 — ⭐ Heatmap: Region × Category Profit
> Diverging RdYlGn heatmap centered at zero, revealing Furniture losses in Central region.

---

## 💡 4 Business Insights

### 1. 🪑 Tables Are a -$17K Profit Drain
Cap discounts at 20%, raise prices, or negotiate better supplier terms. Consider discontinuation if unprofitable.

### 2. 💸 Discounts >40% = Guaranteed Loss
Implement a strict 30% discount ceiling. Require manager approval for anything above 20%.

### 3. 🌍 West Leads Sales, East Leads Efficiency
Study East region's pricing discipline and replicate across underperforming regions.

### 4. 💻 Technology = Profit Champion (17% margin)
Double down on Technology, especially Copiers ($56K from 149 sales). Reduce Furniture's aggressive discounting.

---

## ⭐ Bonus Features

| Feature | Description |
|---------|-------------|
| **Profit Margin Color-Coded Bar** | Red/Orange/Green visualization of margins per category |
| **Region × Category Heatmap** | Diverging colormap highlighting profit/loss zones |

---

## ✅ Deliverables Checklist

- [x] Jupyter notebook with full analysis and comments
- [x] `note.md` with methodology and key findings
- [x] Bar chart of profit by sub-category (negatives highlighted)
- [x] Scatter plot of discount vs profit
- [x] Yearly sales trend line chart
- [x] 4 business insights for profit improvement
- [x] ⭐ Profit margin (%) per category with color-coded bar
- [x] ⭐ Heatmap: Region vs Category showing total profit

---

<p align="center">
  <i>Built with 🐍 Python | 📊 pandas | 🎨 matplotlib + seaborn</i>
</p>
