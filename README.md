# Sales-Analysis-Dashboard
Sales Analysis Dashboard – Common DAX Measures
1. Total Sales
DAX
Copy
Edit
Total Sales = SUM(Sales[SalesAmount])
2. Total Profit
DAX
Copy
Edit
Total Profit = SUM(Sales[Profit])
3. Profit Margin (%)
DAX
Copy
Edit
Profit Margin (%) = DIVIDE([Total Profit], [Total Sales], 0)
4. Total Quantity Sold
DAX
Copy
Edit
Total Quantity = SUM(Sales[Quantity])
5. Average Selling Price
DAX
Copy
Edit
Average Selling Price = AVERAGE(Sales[UnitPrice])
6. Year-over-Year Sales Growth
DAX
Copy
Edit
YoY Sales Growth = 
VAR CurrentYearSales = [Total Sales]
VAR LastYearSales = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
RETURN DIVIDE(CurrentYearSales - LastYearSales, LastYearSales, 0)
7. Top Performing Product
DAX
Copy
Edit
Top Product = 
TOPN(1, SUMMARIZE(Sales, Products[ProductName], "Total", [Total Sales]), [Total Sales], DESC)
