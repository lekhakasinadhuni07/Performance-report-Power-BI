# 📊 Performance Report: Power BI Dashboard
## 🚀 Project Overview
This Power BI dashboard provides a comprehensive performance report, focusing on quantity, sales, and gross profit (GP%) across different countries and product categories. The dashboard enables year-over-year (YoY) comparisons using YTD (Year-to-Date) and PYTD (Prior Year-to-Date) metrics, helping stakeholders track performance trends and make data-driven decisions.

![image Alt](https://github.com/lekhakasinadhuni07/Performance-report-Power-BI/blob/669ed6420d1457a90d4d145be1a89d8cdd3cf95d/Performance_report.png)

## 🔍 Key Features & Functionalities
### 1. Data Sources & ETL Process
📌 **Data Sources:**
- Sales data
- Product details
- Geographical data
- Date dimension table

📌 **Data Transformation (Power Query Editor):**
- Cleaned and formatted raw data
- Created relationships between Sales, Products, and Date tables
- Added custom columns (e.g., YTD vs PYTD calculation)

### 2. DAX Measures & Calculations
📌 **Sales & Quantity Comparisons**
- **YTD Sales**
```dax
YTD_Sales = TOTALYTD([Sales], Dim_Date[Date])
```
- **PYTD Sales (Prior Year-to-Date Sales)**
```dax
PYTD_Sales = CALCULATE([Sales], SAMEPERIODLASTYEAR(Dim_Date[Date]), Dim_Date[Inpast]=TRUE)
```
- **YTD vs PYTD Variance**
```dax
YTD_vs_PYTD = [YTD_Sales] - [PYTD_Sales]
```
- **Gross Profit % Calculation**
```dax
GP% = DIVIDE([Gross Profit], [Sales], 0) * 100
```
### 3. Data Visualization & Charts
I used various Power BI visuals to represent insights effectively:

✅ **KPI Cards:** Display YTD Sales, PYTD Sales, YTD vs PYTD Change, and GP%

✅ **Waterfall Chart:** Shows the increase and decrease in sales quantity over time

✅ **Stacked Column Chart:** Compares YTD vs PYTD sales per month

✅ **Scatter Plot:** Maps Profitability segmentation using GP% vs Quantity

✅ **Tree Map:** Highlights countries with low YTD vs PYTD performance

### 4. Interactive Features & Filters
To enhance user experience and interactivity, I implemented:

🔹 **Slicers:**
- Dropdown slicer for selecting Date (Year & YTD)
- Product Category slicer to filter performance by product type

🔹 Dynamic Measure Switching (Using a SWITCH DAX formula)
- Allows toggling between Gross Profit, Quantity, and Sales KPIs

🔹 Syncing Slicers Across Pages:
- Ensured slicers update all visuals for consistent filtering

### 5. Advanced Techniques & Optimization

💡 Performance Optimization:
- Used aggregated calculations instead of raw row-level data
- Implemented date intelligence functions for YoY analysis

💡 Custom Formatting & UX Enhancements:
- Applied conditional formatting to highlight negative trends
- Used color-coded bars in waterfall charts to indicate growth/decline

## Conclusion & Impact
This dashboard enables business users to:

✔️ Track real-time performance trends in key sales and profitability metrics

✔️ Identify underperforming regions and products using interactive visuals

✔️ Make data-driven decisions to optimize sales strategies

## Next Steps & Portfolio Enhancement
To further enhance this dashboard, I plan to:

📌 Integrate predictive analytics using Power BI AI visuals

📌 Add R or Python scripts for advanced forecasting

📌 Implement custom tooltips and drill-through pages for deeper analysis












