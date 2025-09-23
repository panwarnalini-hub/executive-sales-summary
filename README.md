# Executive Sales Summary (Power BI Dashboard)

## Overview
This Power BI dashboard analyzes Contoso’s sales data (2011–2013 actuals with 2014 forecast).  
It highlights sales performance, profit margins, order patterns, and regional breakdowns through interactive visuals.

## Dataset
- Source: Microsoft Contoso Sales Dataset  
- Period: 2011–2013 (forecast applied for 2014)  
- Tables: Sales, Products, Stores, Calendar, Geography  

## Key Measures
- **Total Sales** = SUM(Sales[SalesAmount])  
- **Total Profit** = SUM(Sales[SalesAmount]) - SUM(Sales[TotalCost])  
- **Profit Margin %** = DIVIDE([Total Profit], [Total Sales], 0)  
- **Orders Count** = COUNTROWS(Sales)  
- **Avg Sales** = AVERAGE(Sales[SalesAmount])  
- **Sales per Order** = DIVIDE([Total Sales], [Orders Count])  
- **Sales per Store** = DIVIDE([Total Sales], DISTINCTCOUNT(Sales[StoreKey]))  
- **Total Quantity** = SUM(Sales[SalesQuantity])  

## Custom Columns
- **MonthSort** = YEAR(Calendar[Date]) * 100 + MONTH(Calendar[Date])  
- **Custom Bin** = SWITCH(TRUE(), ranges for order quantity grouping)  

## Features
- KPI cards for Sales, Profit, Orders, Avg Sales  
- Sales forecast for 2014 using Power BI’s built-in forecasting  
- Order size distribution (histogram with custom bins)  
- Sales breakdown by Continent, Country, Store Type  
- Drillthrough page: Top 5 Stores, Category breakdown, Profitability table  

## Screenshots
### Main Dashboard
![Overview Page](images/overview.png)

### Drillthrough Page
![Drillthrough Page](images/drillthrough.png)

## How to Use
1. Download PBIX File from Google Drive (https://drive.google.com/file/d/153Bu3TIUcZsC0lIOe50sw5nfqKxJBMvu/view?usp=sharing)
2. Open in [Power BI Desktop](https://powerbi.microsoft.com/desktop/).  
3. Use slicers and drillthrough to explore the data.  

## Notes
- Data is **synthetic** (Microsoft Contoso sample).  
- Actuals: 2011–2013, Forecast: 2014.  
