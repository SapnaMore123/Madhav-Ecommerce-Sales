# 📊 Madhav-Ecommerce-Sales | Ecommerce Sales Dashboard (Power BI)


> A compact Power BI report that analyzes ecommerce performance across states, categories, sub-categories, customers, and payment modes—with monthly profit trends and interactive slicers.

---

## 🚀 Highlights
- **KPIs:** Total Sales (Amount), Profit, Quantity, and Average Order Value (AOV)  
- **Trends:** Profit by Month (Jan–Dec)  
- **Breakdowns:**  
  - Sales by State  
  - Quantity by Category (donut)  
  - Sales by Customer  
  - Quantity by Payment Mode (donut)  
  - Profit by Sub-Category  
- **Filters/Slicers:** Quarter (Q1–Q4), State  
- **Design:** Dark gradient theme, rounded cards, modern typography  

---

## 🖥️ Report Pages / Visuals

### KPI Cards
- Total Sales  
- Total Profit  
- Total Quantity  
- Average Order Value (AOV)  

### Bar Charts
- Sales by State  
- Sales by Customer  
- Profit by Sub-Category  

### Donut Charts
- Quantity by Category  
- Quantity by Payment Mode  

### Column Chart
- Profit by Month  

### Slicers
- Quarter (Q1–Q4)  
- State  

---

## 📊 Key Metrics (DAX)

```DAX
-- Total Sales (Amount)
[Total Sales] = SUM ( 'Sales'[Amount] )

-- Total Profit
[Total Profit] = SUM ( 'Sales'[Profit] )

-- Total Quantity
[Total Quantity] = SUM ( 'Sales'[Quantity] )

-- Average Order Value (AOV)
[AOV] = DIVIDE ( [Total Sales], DISTINCTCOUNT ( 'Sales'[OrderID] ) )

-- Profit by Month (for monthly trend chart)
[Profit by Month] =
CALCULATE ( [Total Profit], ALLEXCEPT ( 'Date', 'Date'[Year], 'Date'[Month] ) )

-- Quarter Label (for slicer)
[Quarter] = "Q" & FORMAT ( 'Date'[QuarterOfYear], "0" )
