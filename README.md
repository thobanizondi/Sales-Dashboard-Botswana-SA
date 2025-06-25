Sales-Dashboard-Botswana-SA -- End to End Power BI Bootcamp presented by Pro. Tarcisio from Exodus-Experts

This Power BI project presents an interactive sales dashboard analyzing vehicle sales performance across Botswana and South Africa. The report visualizes key business metrics such as revenue, profit, quantity sold, and performance by brand, model, and city.

Setup Instructions git clone https://github.com/thobanizondi/Sales-Dashboard-Botswana-SA

Import CSV into Power BI Load dataset
Apply transformations
Create insights-driven dashboards

Use Cases
Present Revenue by Country (ZA / BW)  
* View and compare total revenue from South Africa and Botswana using interactive filters and visuals.
Identify Top 3 Cars Sold  
* Track the three best-selling car models based on quantity sold.
Compare Profit × Sales Quantity Between Brands  
* Analyze which car brands yield the highest profit and how it relates to the number of units sold.
Visualize Revenue and Sales by City and Dealer 
* Explore how revenue and quantity vary by geographic location and dealership through map visuals.

Dashboard Features
- Revenue 
- Profit 
- 3 Top Models 
- Sales Quantity
- Location Intelligencer  
- Date Slicers*  
- Country Filter - Switch between Botswana and South Africa views
  
Tools & Technologies
- Power BI Desktop
- DAX - for calculated measures
- Power Query (M Language) - for data transformation
- Bing Maps API - for geographic visuals
- CSV / Excel -  for data input

<img width="406" alt="Sales Dashboard" src="https://github.com/user-attachments/assets/4397df3b-75f7-4a27-8c6c-5db746a55167" />


Data Model Overview
The Power BI dashboard is powered by a star schema consisting of one central fact table (factSales) and two related dimension tables (dimModels and dimDealers). This structure supports optimized reporting and slicing across various sales dimensions.

<img width="688" alt="Data Model-Relationship" src="https://github.com/user-attachments/assets/6e9b131c-1d73-4460-acd8-7f962da650a7" />

Tables and Relationships
factSales (Fact Table)
Holds transactional sales data:
-SaleID: Unique identifier for each sale
-Date: Date of transaction
-DealerID: Foreign key to dimDealers
-ModelID: Foreign key to dimModels
-Quantity: Number of units sold
-Revenue: Total revenue for the transaction
-Profit: Total profit generated

dimModels (Dimension Table)
Describes the car models involved in the sales:
-ModelID: Primary key (joined to factSales)
-Model: Model name (e.g., Polo, Qashqai)
-Brand: Manufacturer (e.g., BMW, Toyota)
-EngineSize (L), Fuel, Segment: Additional model attributes
-Price (USD), Profit (USD): Per-unit financials

dimDealers (Dimension Table)
-Contains dealership information:
-DealerID: Primary key (joined to factSales)
-DealerName: Name of the dealer
-City: City where dealer is located
-Country: Country (Botswana or South Africa)

Relationships
-One-to-many from dimModels[ModelID] → factSales[ModelID]
-One-to-many from dimDealers[DealerID] → factSales[DealerID]

These relationships allow dynamic filtering and aggregation of sales data by model and dealer location, enabling the report’s interactive capabilities (like filtering by brand, country, city, or model).












