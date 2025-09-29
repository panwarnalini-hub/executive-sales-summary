# Measures – Executive Sales Summary (2011-2014)

This file documents all the DAX measures used in the dashboard.

---

## Key KPI Measures

```DAX
Avg Sales = AVERAGE('Sales'[SalesAmount])
Orders Count = COUNTROWS('Sales')
Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)
Sales per Order = DIVIDE([Total Sales], [Orders Count])
Sales per Store = DIVIDE([Total Sales], DISTINCTCOUNT('Sales'[StoreKey]))
```

## Totals
```DAX
Total Sales = SUM('Sales'[SalesAmount])
Total Profit = SUM('Sales'[SalesAmount]) - SUM('Sales'[TotalCost])
Total Quantity = SUM('Sales'[SalesQuantity])
```

## Custom Bins for Sales Quantity
```DAX
Custom Bin =
SWITCH(
    TRUE(),
    'Sales'[SalesQuantity] <= 50, "0–50",
    'Sales'[SalesQuantity] <= 100, "51–100",
    'Sales'[SalesQuantity] <= 500, "101–500",
    "500+"
)
```
