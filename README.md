# Superstore Discount Impact and Regional Profitability Analysis

## Overview:
This project audits transaction-level sales data from a retail superstore to uncover where the business is actually profitable, where it's losing money, and why. Rather than relying on sales volume alone as a success metric, this analysis digs into discounting behavior, regional performance, shipping practices, seasonality, and customer segments to surface actionable insights for leadership.

## Why This Topic?
Retailers often chase sales volume as a success metric, but high sales don't guarantee high profit — discounting, shipping costs, and regional inefficiencies can quietly erode margins. This project investigates a superstore's transaction data to identify where the business is profitable, where it's wasting money, and why — so leadership can make targeted decisions on pricing, discounting policy, and regional strategy instead of guessing.

## Dataset
- **Source:** [Superstore Sales Dataset (Kaggle)](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
- **Size:** ~9,994 rows, 21 columns
- **Fields include:** Order Date, Ship Date, Ship Mode, Segment, Region, State, City, Category,
  Sub-Category, Sales, Quantity, Discount, Profit, Postal Code
- **Note:** A small number of missing values and duplicate rows were synthetically introduced
  into the otherwise clean dataset to demonstrate the full data-cleaning workflow.

## Key Business Questions

1. Which product categories/sub-categories are profitable vs. loss-making?
2. Does discounting actually hurt profit?
3. Which regions/states are most efficient (profit per order) vs. just high-volume?
4. Does shipping mode affect profitability or delivery time?
5. Is there a seasonal pattern in sales and profit?
6. Which customer segment (Consumer, Corporate, or Home Office) generates the best profit margin per order, and should marketing/sales resources be reallocated toward it?

## Project Workflow

1. **Problem Statement & Dataset Overview** — dataset structure, features, and business context.
2. **Data Cleaning & Quality Audit**
   - Missing value audit (before/after): Postal Code imputed with a placeholder (0); Sales
     imputed using the median Sales per Sub-Category
   - Duplicate rows identified and removed
   - Order Date/Ship Date converted to datetime; key categorical columns converted to `category` dtype
3. **Exploratory Data Analysis & Manipulation**
   - Summary statistics (Mean, Median, Std Dev, IQR, Min, Max)
   - Feature engineering: date components, Shipping Delay, Profit Margin (%)
   - Six groupby-based business questions answered (category, discount, region, shipping mode,
     seasonality, segment)
4. **Distribution & Visual Analysis**
   - Histogram/KDE — Profit distribution
   - Bar chart — Total Profit by Sub-Category
   - Boxplot — Profit across Discount Ranges (outlier detection)
   - Correlation heatmap — Sales, Discount, Profit, Shipping Delay
   - Scatter plot — Sales vs Profit colored by Discount
   - Comments under every chart
5. **Key Business Takeaways** — 5 data-backed findings + overall conclusion

## Key Findings

- Discounts above ~20% consistently push median profit into negative territory; 31–50%
  discounts are the most damaging band.
- Certain sub-categories (e.g., Tables, Bookcases) lose money despite strong sales volume.
- Some regions/states generate high sales but low profit-per-order — efficiency doesn't track
  with revenue size.
- Shipping mode has little to no measurable effect on profit margin.
- The **Home Office** segment delivers the strongest profit-per-order, making it the top
  candidate for reallocated marketing/sales resources.

## Tools & Libraries
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Jupyter Notebook

## Project Structure
superstore-discount-profitability-analysis/
│
├── data/
│ └── Sample_Superstore_messy.csv
├── notebook/
│ └── superstore_analysis.ipynb
└── README.md

## Author
Name: Imaan Mutayyab 
Organization: Aurat Tech x Data Camp 
Cluster/Track: C2-Data Scientist 
ID: DC-442 

