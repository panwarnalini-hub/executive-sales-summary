# Data Dictionary - Executive Sales Summary (2011-2014)

This file describes the calculated columns, hierarchies, and an example dataset snapshot.

---

## Calculated Columns

### Calendar Hierarchy

```DAX
Year = YEAR('Calendar'[Date])
Month = FORMAT('Calendar'[Date], "MMMM")
Month Number = MONTH('Calendar'[Date])  // Used to sort Month correctly
Quarter = "Q" & FORMAT('Calendar'[Date], "Q")
```

### Example Data Snapshot

| StoreType | StoreName                | Year | Orders Count | Total Sales | Total Quantity | Total Profit | Profit Margin % |
| --------- | ------------------------ | ---- | ------------ | ----------- | -------------- | ------------ | --------------- |
| Store     | Contoso Albany Store     | 2011 | 2,454        | \$7,081,979 | 26,353         | \$4,095,308  | 0.58            |
| Store     | Contoso Albany Store     | 2012 | 1,472        | \$4,727,609 | 21,363         | \$2,737,688  | 0.58            |
| Store     | Contoso Albany Store     | 2013 | 1,097        | \$4,169,224 | 22,270         | \$2,356,803  | 0.57            |
| Store     | Contoso Alexandria Store | 2011 | 2,444        | \$6,612,399 | 26,247         | \$3,804,900  | 0.58            |
| Store     | Contoso Alexandria Store | 2012 | 1,397        | \$4,769,138 | 21,491         | \$2,772,162  | 0.58            |

### Notes

Date Hierarchy was built manually (Year, Quarter, Month, Month Number) for correct sorting and drill-down.

Forecast (2014) was generated using the Power BI forecasting feature on Total Sales.

Custom Bin was created to analyze Order Size Distribution.
