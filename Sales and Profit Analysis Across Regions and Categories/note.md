# 📝 Note: Sales and Profit Analysis Across Regions and Categories

## Methodology

### 1. Data Loading & Quality Assessment
- Loaded `Sample - Superstore.csv` containing **9,994 orders** across 21 columns
- **No missing values** detected; no duplicate rows
- Dataset covers US retail sales from **2014 to 2017** across 4 regions

### 2. Data Preprocessing
- **Order Date / Ship Date**: Converted from string to `datetime64`
- **days_to_ship**: Calculated as `Ship Date - Order Date` (avg ~4 days)
- Extracted **year** and **month** features for temporal analysis

### 3. Multi-Level Aggregation
Grouped and aggregated total Sales and Profit by:
- **Region** — West, East, Central, South
- **Category** — Technology, Office Supplies, Furniture
- **Sub-Category** — 17 product sub-categories
- **Region × Category** cross-tabulation with profit margins

### 4. Negative Profit Detection
- Identified sub-categories where **total profit is negative** (loss-making)
- Analyzed individual loss-making orders and their correlation with discounts

### 5. Discount vs Profit Analysis
- Created discount bins (0-10%, 10-20%, etc.) and analyzed average profit per bin
- Scatter plot with trend line showing strong negative correlation
- Orders with >40% discount almost always lose money

### 6. Yearly Trend Analysis
- Year-over-year sales and profit from 2014 to 2017
- Calculated growth rates showing ~20% annual sales increase

### 7. Visualizations Created

| # | Chart Type | Description | File |
|---|-----------|-------------|------|
| 1 | Horizontal Bar | Profit by Sub-Category (negatives in red) | `chart1_profit_by_subcategory.png` |
| 2 | Scatter Plot | Discount vs Profit relationship | `chart2_discount_vs_profit.png` |
| 3 | Bar + Line | Yearly Sales & Profit Trend (dual-axis) | `chart3_yearly_sales_trend.png` |
| 4 | Dual Bar | Sales & Profit by Region (side by side) | `chart4_region_sales_profit.png` |
| 5 | Color-Coded Bar ⭐ | Profit Margin (%) by Category | `chart5_profit_margin_category.png` |
| 6 | Heatmap ⭐ | Region × Category Total Profit | `chart6_heatmap_region_category.png` |

### 8. Bonus Features
- **Profit Margin Color-Coded Bar**: Red (<5%), Orange (5-12%), Green (>12%) per category
- **Region × Category Heatmap**: RdYlGn diverging colormap centered at zero to highlight profit/loss zones

---

## Key Findings

### 🌍 Regional Performance
- **West** leads in sales (~$725K) but not necessarily in profit margin
- **South** has the lowest sales (~$391K)
- All 4 regions are profitable, but margin efficiency varies

### 📦 Category Performance
- **Technology** is the most profitable category (~$145K profit, ~17% margin)
- **Office Supplies** generates solid profit with good margins
- **Furniture** has the lowest margin (~2%) despite significant sales volume

### 📉 Sub-Category Insights
- **Tables** is the biggest profit drain: ~-$17K loss
- **Bookcases** also show negative or minimal profit
- **Copiers** is the most efficient: ~$56K profit from just ~149 sales
- **Phones** and **Chairs** are strong performers

### 💸 Discount Impact
- Correlation between Discount and Profit is **strongly negative**
- Orders with **>40% discount** almost always result in losses
- The current discounting strategy is directly eroding profitability

### 📅 Yearly Trends
- **2017** was the peak year for sales (~$733K)
- Consistent ~20% year-over-year growth from 2014–2017
- Profit growth tracks sales growth but with more volatility

---

## 💡 4 Business Insights for Profit Improvement

### 1. Tables Sub-Category Is a Major Profit Drain
Tables generates ~$-17K loss despite substantial sales. Root causes include over-discounting and high shipping costs. **Action**: Raise prices, cap discounts at 20%, or negotiate better supplier terms. Consider discontinuing if unprofitable.

### 2. Heavy Discounts (>40%) Destroy Profit
Scatter plot clearly shows orders above 40% discount almost always lose money. **Action**: Implement strict 30% discount ceiling with manager approval for anything above 20%.

### 3. West Leads Sales but East Leads Efficiency
West generates the most revenue but East achieves better profit margins. **Action**: Study East's pricing discipline and apply those practices across South and Central regions.

### 4. Technology Is the Profit Champion
Technology achieves ~17% profit margin vs Furniture's ~2%. Copiers alone generate $56K from 149 orders. **Action**: Allocate more marketing budget and shelf space to Technology, especially Copiers. Reduce Furniture's aggressive discounting.

---

## Technical Stack
- **Python 3.13**: pandas, matplotlib, seaborn, numpy
- **Environment**: Jupyter Notebook
- **Dataset**: `Sample - Superstore.csv` (9,994 rows × 21 columns)
- **Source**: [Kaggle — Superstore Dataset](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)

---

*Analysis completed on April 2026*
