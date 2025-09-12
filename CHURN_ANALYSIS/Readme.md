Churn Analysis Dashboard
This Power BI project provides insights into customer churn trends, focusing on active/inactive members, 
exit customers, retention, and credit card usage. The dashboard highlights churn patterns by demographics, time, and customer categories.

📂 Data Model
Tables Used:
Bank_Churn
Contains customer-level details such as CreditScore, Age, Balance, Tenure, Products, HasCrCard, IsActiveMember, 
EstimatedSalary, Exit status, and Bank DOJ.

Customer_Info
Maps CustomerId → Surname.

Geography
Maps GeographyID → GeographyLocation.

Gender
Maps GenderID → GenderCategory.

Customer Exit
Maps ExitID → ExitCategory (Exit / Retain).

Credit Card
Maps CreditID → Category (Credit Card Holder / Non Credit Card Holder).

Active Customers
Maps ActiveID → ActiveCategory (Active / Inactive Member).

Calendar
Date table used for time intelligence (Month, Year, Previous Month).

🧮 DAX Measures
-- Total Customers
Total Customers = COUNTROWS(Bank_Churn)

-- Active Members
Active Members = 
CALCULATE(
    COUNTROWS(Bank_Churn),
    Bank_Churn[IsActiveMember] = 1
)

-- Inactive Members
Inactive Members =
CALCULATE(
    COUNTROWS(Bank_Churn),
    Bank_Churn[IsActiveMember] = 0
)

-- Credit Card Holders
Credit Card Holders =
CALCULATE(
    COUNTROWS(Bank_Churn),
    Bank_Churn[HasCrCard] = 1
)

-- Non Credit Card Holders
Non Credit Card Holders =
CALCULATE(
    COUNTROWS(Bank_Churn),
    Bank_Churn[HasCrCard] = 0
)

-- Exit Customers
Exit Customers =
CALCULATE(
    SUM(Bank_Churn[ExitID]),
    Bank_Churn[ExitID] = 1
)

-- Retain Customers
Retain Customer =
CALCULATE(
    COUNTROWS(Bank_Churn),
    Bank_Churn[ExitID] = 0
)

-- Join Month (for slicer/visuals)
JoinMonth = FORMAT(SELECTEDVALUE(Bank_Churn[Bank DOJ]), "mmm")

-- Previous Month Exit Customers
Previous Month Exit Customers =
CALCULATE(
    [Exit Customers],
    PREVIOUSMONTH('Calendar'[Date])
)

📊 Visualizations Used

KPI Cards
Total Customers
Active Members
Inactive Members
Credit Card Holders
Non Credit Card Holders
Exit Customers
Retain Customers

Bar Chart (Clustered Column)
Total Customers by Month (Active vs Inactive).
Line Chart
Exit Customers trend by month with Previous Month comparison.

Donut Chart
Exit Customers by Gender.

Bar Chart (Horizontal)
Exit Customers by Credit Type Category (Good, Fair, Very Good, Excellent, Poor).

Slicers (Filters)
Bank DOJ
Month Name

Geography Location
Active Category
Gender Category

🎨 Shapes and Headings

Dashboard Title: "CUSTOMER CHURN ANALYSIS" (Shape/Heading)
Section Cards: KPIs displayed in rectangular cards at the top.

Color Coding:
Blue for Active/Positive measures.
Yellow for highlights (KPI background).
Pie/donut with distinct gender colors.

🚀 Insights
Majority of churn occurs among Inactive Members.
Credit Card Holders form the largest group but also contribute significantly to churn.
Gender distribution shows slightly higher churn among Male customers.
Exit rates peaked in December and September.
Customers with "Good" and "Fair" credit types exit more often than others.

<img width="1238" height="671" alt="Screenshot 2025-09-12 090145" src="https://github.com/user-attachments/assets/8d0b9dbb-eead-47cf-8a94-52d3c166e755" />
