Finance Dashboard 📊

This repository contains a Finance Dashboard built in Power BI, designed to provide insights 
into sales, profit, discounts, and cost of goods sold (COGS) across multiple dimensions such as 
products, segments, and locations.

🔗 Live Dashboard: View on Power BI
https://app.powerbi.com/groups/me/reports/0d2d99d0-ff04-493f-86ba-d8c31398387e/bbcad33b196a40c7ba87?experience=power-bi

📂 Dataset: Finance Data (Kaggle)

 When clicking on the Finance Dashboard image (top left corner), it will navigate to the following dataset link: https://www.kaggle.com/datasets/nitindatta/finance-data

📌 Features
The dashboard is divided into three main sections accessible through top navigation buttons:
. Navigation
The dashboard contains three Page navigation buttons visible on all pages(CTRL+ENTER) to view:
- Revenue: Displays sales, profit, discount, and COGS breakdown.
- Location: Shows data by country including COGS, discounts, profit, and map visualization.
- Details: Provides deeper insights by segment and product.


1. Revenue Page

    KPI Cards → Total Sales, Profit, Discounts
    Slicers → Segment, Year
    Animated Bar Chart → COGS by Country & Date
    Gauge Chart → Product-wise Units Sold
    Tree Map → Sales by Products
    Donut Chart → Gross Sales by Segment

2. Location Page

    KPI Cards → Total COGS, Discounts
    Slicer → Country
    Cylinder Gauge → Units Sold by Country
    Map → Country-wise Discounts
    Area Chart → Profit Trend by Country

3. Details Page

    Line & Cluster Chart → Product-Year COGS vs Profit
    Super Filter → Products
    Table with Conditional Formatting → Segment-wise Profit, COGS, Sales
    Funnel Chart → Segment-Year COGS vs Profit
    Gauge Chart → Units Sold by Segment

🛠️ Tools & Technologies

Power BI (Data Modeling & Visualizations)
Excel/CSV from Kaggle Finance Dataset
DAX (for calculated measures & KPIs)

DAX Calculations 

🔹 Core KPIs

    
    Total Sales = SUM(FinanceData[Sales])

    Total Profit = SUM(FinanceData[Profit])
  
    Total Discounts = SUM(FinanceData[Discount])
   
    Total COGS = SUM(FinanceData[COGS])
 
    Units Sold = SUM(FinanceData[Units])

🔹 Time Intelligence

   
    LY Sales = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(FinanceData[Date]))
   
    CY Profit = CALCULATE([Total Profit], YEAR(FinanceData[Date]) = YEAR(TODAY()))
  
    LY Discount = CALCULATE([Total Discounts], SAMEPERIODLASTYEAR(FinanceData[Date]))

    YoY Sales % = 6DIVIDE([Total Sales] - [LY Sales], [LY Sales], 0)

🔹 By Segment / Product / Country

  
    Sales by Segment = SUM(FinanceData[Sales])

    Profit by Segment = SUM(FinanceData[Profit])

    COGS by Segment = SUM(FinanceData[COGS])
  
    Units Sold by Segment = SUM(FinanceData[Units])
  
    Sales by Product = SUM(FinanceData[Sales])
   
    Sales by Country = SUM(FinanceData[Sales])

🔹 Ratios / KPIs


    Gross Margin % = DIVIDE([Total Profit], [Total Sales], 0)

    Discount % = DIVIDE([Total Discounts], [Total Sales], 0)
  
    Profit % = DIVIDE([Total Profit], [Total Sales], 0)
  
    COGS % = DIVIDE([Total COGS], [Total Sales], 0)

🔹 For Charts

 
    Product-Year COGS = SUM(FinanceData[COGS])
   
    Product-Year Profit = SUM(FinanceData[Profit])
 
    Segment-Year COGS = SUM(FinanceData[COGS])
 
    Segment-Year Profit = SUM(FinanceData[Profit])

📊 Key Insights

    Identify top-performing products by sales and profit.
    Track discount impact on overall revenue.
    Compare COGS vs Profit by segment and year.
    Visualize country-level performance with maps and gauges.

<img width="1224" height="670" alt="image" src="https://github.com/user-attachments/assets/b798d546-070a-4c39-b692-989154481962" />
<img width="1231" height="671" alt="image" src="https://github.com/user-attachments/assets/fa59045b-59f6-4602-a452-23178a8ec130" />
<img width="1193" height="656" alt="image" src="https://github.com/user-attachments/assets/f07f1834-ee72-4727-80df-41cdddefde57" />


