# Blinkit Sales & Performance Analysis Dashboard
![Dashboard Preview] 


## 📊 Project Overview
This Power BI project provides a comprehensive analysis of Blinkit's sales performance, customer satisfaction (ratings), and inventory distribution. The dashboard is designed to help stakeholders understand key trends across different outlet locations, outlet sizes, and item categories.

## 🎯 Business Requirement
To conduct a detailed analysis of "Blinkit" performance to identify:
1.  **Total Sales & Revenue:** Understanding the financial scope.
2.  **Item Popularity:** Which item types perform best?
3.  **Outlet Performance:** How do different store sizes and location tiers compare?
4.  **Consumer Preferences:** Analysis of Fat Content (Low Fat vs. Regular).
5.  **Historical Trend:** Sales trajectory over the years (2012-2018).

## 🛠️ Data Cleaning & Processing
Before visualization, the raw data underwent the following transformation steps:
* **Data Quality Check:** Checked for NULL values in `Item_Weight` and `Outlet_Size`.
* **Data Standardization:** Replaced inconsistent values in the `Item_Fat_Content` column (e.g., replaced "LF" and "low fat" with "Low Fat", and "reg" with "Regular") to ensure the Donut chart analysis is accurate.
* **Measure Creation:** Created a dedicated table for measures to keep the model organized.

## 🧮 KPI Metrics & DAX Calculations
The following Key Performance Indicators (KPIs) were created using DAX (Data Analysis Expressions):

### 1. Total Sales
Calculates the total revenue generated from all items sold.
```dax
Total Sales = SUM('Blinkit Data'[Item_Outlet_Sales]).

**### 2. No. of Items**
Calculates the total count of distinct items sold.
Code snippet
No. of Items = COUNT('Blinkit Data'[Item_Identifier])

**### 3. Average Sales**
Calculates the average revenue per sale.
Code snippet
Avg Sales = AVERAGE('Blinkit Data'[Item_Outlet_Sales])

**### 4. Average Ratings**
Calculates the average customer rating for items.
Code snippet
Avg Ratings = AVERAGE('Blinkit Data'[Item_Visibility])
(Note: Depending on your specific column names, Item_Visibility might be Item_Rating in your source file).
📈 Visualizations Used

1. Filter Panel (Slicers)
Located on the left sidebar, allowing users to slice data by:
•	Outlet Location Type: (e.g., Tier 1, Tier 2, Tier 3)
•	Outlet Size: (Small, Medium, High)
•	Outlet Type: (Grocery Store, Supermarket Type 1/2/3)

2. KPI Cards
Top-level metrics displaying real-time snapshots of:
•	$336.40K Total Sales
•	2,388 Number of Items
•	$141 Average Sales
•	3.9 Average Ratings

3. Granular Analysis (Center Section)
•	Donut Chart (Fat Content): Visualizes the proportion of Low Fat vs. Regular items.
•	Bar Chart (Item Types): Ranks product categories (Fruits, Snacks, Household, etc.) based on Total Sales/Revenue.
o	Feature: Includes a custom navigation menu (Buttons) to toggle the view between Total Sales, Avg Sales, Avg Ratings, and No. of Items.
•	Clustered Bar (Fat by Outlet): Compares fat content sales specifically within the selected Outlet Tier.

4. Outlet Performance (Right Section)
•	Line Chart (Outlet Establishment): Shows the historical trend of sales from 2012 to 2018, highlighting growth or decline phases.
•	Donut Chart (Outlet Size): Break down of sales by store size (Small vs. Medium vs. High).
•	Funnel/Bar Chart (Outlet Location): Distribution of sales across different Tier locations.
•	Matrix Table (Outlet Type): A detailed tabular view comparing Grocery Stores vs. Supermarkets across all key metrics (Total Sales, Avg Sales, Avg Ratings, and Item Visibility).
🚀 Key Insights from the Dashboard
•	Sales Trend: There is a noticeable sales performance trajectory peaking around 2016 before a decline leading into 2018.
•	Category Dominance: Fruits and Snack Foods are the top-performing categories in terms of revenue.
•	Fat Content: There is a significant market for "Low Fat" products, almost rivaling "Regular" products in certain cuts of the data.
•	Tier 1 dominance: Tier 1 locations (as shown in the filter context) account for a massive portion of the sales ($336.40K).
💻 Tech Stack
•	Tool: Microsoft Power BI Desktop
•	Language: DAX (Data Analysis Expressions)
•	Data Source: Excel/CSV (Blinkit Sales Data)


