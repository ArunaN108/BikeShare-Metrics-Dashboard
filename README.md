# BikeShare-Metrics-Dashboard
Power BI, SQL Server, and Excel files

# Project Title

A brief description of what this project does and who it's for

# Toman BikeShare Metrics Dashboard

### Project Overview

This project focuses on creating a comprehensive Metrics and Development Dashboard in Power BI. The goal is to visualize key performance metrics related to bike-sharing services. The project involved data preparation, creating dynamic visualizations, using DAX formulas, and building interactive reports to uncover actionable insights.


### Objectives

This dashboard provides an analysis of:

- Hourly Revenue Analysis: Identify revenue patterns throughout the day.
- Profit and Revenue Trends: Track performance over time.
- Seasonal Revenue : Examine revenue variations by season.
- Rider Demographics: Explore rider types (casual vs. registered).


### Process Summary

#### Step 1 : Connect to SQL Server
- Open Microsoft SQL Server and connect to the database server.
- Create a new database named "BikeShare_Data".
- Import the Excel files containing:
      
      1. cost_table
      2. bike_share_yr_0 (Year 2021 data)
      3. bike_share_yr_1 (Year 2022 data)

      
#### Step 2: Data Preparation in SQL
- Combine Tables:

      1. Use the UNION function to append bike_share_yr_0 and bike_share_yr_1 into a single dataset.
      2. Create a Common Table Expression (CTE) named 'bikecte' to hold the combined data.


- Join with Cost Data:

      Perform a LEFT JOIN between 'bikecte' and 'cost_table'

- Calculate Metrics:

  Add computed columns for Revenue and Profit using the formulas:

      Revenue = riders * price
      Profit = (riders * price) - (COGS * riders)      

- Finalize Data:

  Execute the SQL script and prepare the final dataset for visualization in Power BI. 

## SQL Query Snapshot (SQL Server) 

![BikeShare SQL Quuery](https://github.com/user-attachments/assets/671613a8-dfd4-4928-8c73-3eaf5bd22b8b)


#### Step 3: Import Data to Power BI
- Connect Power BI to the SQL Server database.
- Load the final table using appropriate server 
  credentials  

 
 #### Step 4: Data Transformation in Power Query

- Open Power Query Editor and:

  Extract the year values from the dteday column:
    
      Use a Conditional Column to transform Year 0 into 2021 and Year 1 into 2022.
  Alternatively, create a New Column directly in the Table View using DAX :

      Year = Query1[dteday].[Year]
- Ensure data types are accurate.
- Apply transformations, then click Close & Apply to load the prepared data.  


#### Step 5: Data Visualization in Power BI
- Key Metrics Cards: Create three cards for:
    1. Total Revenue: $15M
    2. Total Profit: $10.45M
    3. Total Riders: 3M 
    
 
- Visualizations:  

    1. Matrix Table: Display revenue by hour and weekday.
    2. Line and Clustered Column Chart: Show riders, profit, and revenue trends by year and month.
    3. Bar Chart: Visualize revenue by season.
    4. Donut Chart: Illustrate rider demographics (Casual: 18.83%, Registered: 81.17%).
    5. Slicer: Add a slicer for year selection (2021 or 2022).
    
    
#### Step 6: Create a DAX measure for Profit Margin:
DAX

    Profit Margin = (SUM(Query1[revenue]) - SUM(Query1[profit])) / SUM(Query1[profit])


#### Step 7: Formatting

- Apply consistent currency formatting to revenue and profit metrics.
- Add titles and images to enhance clarity.        

 
 # Report Snapshot (Power BI DESKTOP)

 ![Bike Share Metrics Dashboard](https://github.com/user-attachments/assets/d9edb778-2049-483c-a044-2e5eb3a5a4f8)


# Insights

A one page report was created on Power BI Desktop

Following inferences can be drawn from the dashboard;


####  Revenue Trends:

- Peak revenue occurs during midday (12 PM - 2 PM) and early evening (5 PM - 7 PM).
- Season 3 (Fall) generated the highest revenue ($4.9M).


#### Rider Demographics:

- 81.17% registered riders and 18.83% casual riders.

#### Profitability: 
- Total profit of $10.45M with a 0.45% profit margin.


## Recommendations:

 - Pricing Strategies:  Consider a 10-15% price increase during peak hours to maximize revenue and offer lower pricing for casual riders to attract more occasional users.


- Marketing Initiatives:  Target casual riders through promotional campaigns and seasonal discounts.
 

- Operational Improvements: Optimize bike availability during peak hours and high-demand seasons.

- Technology Integration: Leverage mobile apps and real-time tracking to improve user experience.



## Tools and Skills Demonstrated
- Tools: SQL, Power BI, DAX, Excel
- Skills: SQL for Data Manipulation,
  Power BI for Interactive visualizations         


## Conclusion
This project demonstrates my ability to transform raw data into valuable insights through dynamic Power BI visualizations. It highlights expertise in SQL, DAX, and business intelligence, showcasing my capacity to drive data-informed decision-making.
