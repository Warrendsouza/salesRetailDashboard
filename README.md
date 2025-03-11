# salesRetailDashboard


# Retail Sales Performance Analysis - Power BI Project Guide

## Project Overview
This Power BI project provides comprehensive analysis of retail sales performance across different regions, stores, product categories, and time periods. It will help identify trends, compare performance, and generate actionable insights to optimize sales strategies.

## Dataset Description
The dataset contains retail sales data with the following structure:
- **Region**: Geographic region (Northeast, Southeast, Midwest, West)
- **Store**: Store location within each region
- **Date**: Sale date 
- **Product_Category**: Category of product (Electronics, Home, Apparel)
- **Product**: Specific product name
- **Units_Sold**: Number of units sold
- **Unit_Price**: Selling price per unit
- **Cost_Per_Unit**: Cost price per unit
- **Promotion**: Promotional campaign (if applicable)

## Power BI Project Setup

### Step 1: Import Data
1. Open Power BI Desktop
2. Click "Get Data" > "Text/CSV"
3. Navigate to where you saved the sales data CSV file
4. Select the file and click "Load"

### Step 2: Data Transformation
In Power Query Editor:
1. Change "Date" column to Date data type
2. Create calculated columns:
   - **Revenue** = Units_Sold * Unit_Price
   - **Cost** = Units_Sold * Cost_Per_Unit
   - **Profit** = Revenue - Cost
   - **Profit_Margin** = Profit / Revenue

### Step 3: Create Date Table
Create a separate date dimension table:
1. Go to "Modeling" tab > "New Table"
2. Create a date table with the formula:
   ```
   Date = CALENDAR(MIN(Sales[Date]), MAX(Sales[Date]))
   ```
3. Add columns for Day, Week, Month, Quarter, Year

### Step 4: Build Data Model
1. Create relationships:
   - Connect main sales table to date table (one-to-many)
2. Create hierarchies:
   - Geography hierarchy: Region > Store
   - Product hierarchy: Product_Category > Product
   - Date hierarchy: Year > Quarter > Month > Day

### Step 5: Create Measures
Create the following DAX measures:
```
Total Revenue = SUM(Sales[Revenue])
Total Cost = SUM(Sales[Cost])
Total Profit = SUM(Sales[Profit])
Avg Profit Margin = AVERAGE(Sales[Profit_Margin])
Units Sold = SUM(Sales[Units_Sold])
```

## Dashboard Development

### Page 1: Executive Summary
Create a dashboard with:

1. **KPI Cards**:
   - Total Revenue
   - Total Profit
   - Average Profit Margin
   - Total Units Sold

2. **Revenue by Region (Pie Chart)**
   - Shows revenue distribution across regions

3. **Top Products by Revenue (Bar Chart)**
   - Displays top 5 products by revenue

4. **Daily Sales Trend (Line Chart)**
   - Shows daily revenue trend
   - Add trendline

5. **Profit Margin by Category (Column Chart)**
   - Compares profit margins across product categories

### Page 2: Regional Performance

1. **Map Visualization**:
   - Regional performance with color intensity based on revenue

2. **Region Comparison Matrix (Table)**:
   - Columns: Region, Revenue, Units Sold, Profit, Profit Margin
   - Apply conditional formatting

3. **Top Store by Region (Bar Chart)**:
   - Shows top performing store in each region

4. **Region Performance Comparison (Column Chart)**:
   - Side-by-side comparison of key metrics by region

### Page 3: Product Analysis

1. **Product Category Performance (Donut Chart)**:
   - Revenue breakdown by product category

2. **Product Sales Matrix (Table)**:
   - Product, Category, Units Sold, Revenue, Profit, Profit Margin
   - Sort by Revenue (descending)

3. **Units Sold vs. Profit (Scatter Plot)**:
   - X-axis: Units Sold
   - Y-axis: Profit
   - Size: Revenue
   - Color: Product Category

4. **Promotion Impact (Column Chart)**:
   - Compare average units sold with/without promotions
   - Group by product category

### Page 4: Time Analysis

1. **Daily Sales Trend (Area Chart)**:
   - Shows revenue trend over time
   - Include day of week analysis

2. **Day of Week Performance (Column Chart)**:
   - Average revenue by day of week

3. **Promotion Calendar View**:
   - Timeline showing when promotions were active
   - Revenue overlay

4. **Week-over-Week Comparison (Line Chart)**:
   - Compare performance to previous week

## Advanced Features

### Interactive Elements
Add these interactive elements:

1. **Slicers**:
   - Region slicer
   - Store slicer
   - Product Category slicer
   - Date range slicer
   - Promotion filter

2. **Drill-through Pages**:
   - Create detailed drill-through for:
     - Store details
     - Product details

3. **Bookmarks**:
   - Create bookmarks for different analytical views

### Advanced Analytics

1. **Forecast Analysis**:
   - Add forecasting to sales trend for next 7 days

2. **What-If Analysis**:
   - Create parameter for price adjustment scenarios
   - Show impact on revenue and profit

3. **Anomaly Detection**:
   - Highlight outliers in daily sales

## Key Insights Expected

After building this Power BI project, you'll be able to identify:

1. **Revenue Drivers**:
   - Which regions, stores, and products generate the most revenue
   - Impact of promotions on sales

2. **Profitability Analysis**:
   - Most and least profitable products and categories
   - Relationship between sales volume and profitability

3. **Performance Patterns**:
   - Day of week patterns
   - Promotional effectiveness
   - Regional variations

4. **Optimization Opportunities**:
   - Underperforming stores or products
   - High-margin products to focus on
   - Optimal promotion strategies

## Data Refresh & Sharing

1. **Scheduled Refresh**:
   - Schedule daily refresh if publishing to Power BI Service

2. **Dashboard Sharing Options**:
   - Publish to Power BI Service
   - Set up email subscriptions for stakeholders
   - Create mobile view for on-the-go access

## Next Steps for Enhancement

1. Add customer data for customer segmentation analysis
2. Incorporate inventory data to analyze stock levels against sales
3. Add competitor pricing data for competitive analysis
4. Implement more advanced forecasting models



![image](https://github.com/user-attachments/assets/9e1162d9-8c87-4af3-afa1-604dddde4ee3)
