# Analyzing Sales And Financial Performance For AtliQ Tech.

![intro_picture](https://github.com/user-attachments/assets/51aaee61-a52a-4b86-88ed-26a37ac3f341)

### Introduction
AtliQ Technologies is a leading manufacturer of computer hardware in India, distributing products to customers in various countries. As part of their rapid expansion strategy, AtliQ aims to enhance market presence and operational efficiency. The aim of this project is to analyze the company sales data and make a comprehensive report that will provide insights to drive strategic decision-making and support AtliQ's growth objectives.

### Problem Statement
The first step is to define the problem. The business Objectives that I have to tackle are:
1. What are the top 10 products based on the percentage increase in their net sales from 2020 to 2021?

2. Generate a "Division" report to present the net sales data for 2020 and 2021, along with the growth percentage.

3. Which products are ranked in the top 5 and bottom 5 in terms of quantity sold?

4. What are the new products that Atliq began selling in 2021?

5. What are the top 5 countries in terms of net sales in 2021?

### Data Sources
The data for this project was provided in the form of several key datasets. It include dimensional tables and fact tables which are integral to understanding various aspects of the company's operation.

- Dim_Customer: This table contains detailed information about AtliQ Technologies' customers.
- Dim_Product: This table provides information on the products manufactured and sold by AtliQ Technologies.
- Dim_Market: This table includes data related to the different countries where AtliQ Technologies operates.
- Fact_Sales_Monthly: This fact table captures the monthly sales data. It includes quantitative data on sales transactions, it also includes the freight cost and manufacturing cost.

### Tools

For this project, Microsoft Excel with its powerful features such as Power Query, Power Pivot and Pivot Tables was utilized for all data analysis tasks. Excel served as the primary tool for integrating, analyzing, and visualizing sales and financial data, providing a comprehensive platform for developing insights and generating reports.

### Methodology

1. Data Importation: I downloaded the four csv files containing the datasets and imported them into Power Query for transformation.
   ![data_sources](https://github.com/user-attachments/assets/2d28427e-9b1e-4468-8527-6331bc6f2691)

2. Data Cleaning and Transformation: Used Power Query to clean and transform raw data into usable format
   - Handled missing values.
   - Treated data inconsistency.
   - Removed duplicates and formatted headers with correct data types.

3. Data Modeling: Created relationships between different data sources using Power Pivot.
   ![data_model](https://github.com/user-attachments/assets/48e903ac-7403-4d9e-a724-da1da2ef8a8e)

4. DAX Measures: I created some DAX measures to enhance my analysis. These measures provided advanced calculations and aggregations that were essential for deriving deeper insights from the data.
   - **Total Net Sales**:
     ```dax
     Total Net Sales = SUM(fact_sales_monthly[net_sales_amount])
     
   - **Total Net Sales in 2019**:
     ```dax
     Total Net Sales = SUM(fact_sales_monthly[net_sales_amount], dim_date[FY]="2019")
     
   - **Total Net Sales in 2020**:
     ```dax
     Total Net Sales = SUM(fact_sales_monthly[net_sales_amount], dim_date[FY]="2020")

   - **Total Net Sales in 2021**:
     ```dax
     Total Net Sales = SUM(fact_sales_monthly[net_sales_amount], dim_date[FY]="2021")
     
    - **Other Measures**:
     ```dax
     COGS = SUM(fact_sales_monthly[Total_cogs])
     Gross Margin = fact_sales_monthly[Net Sales]-fact_sales_monthly[COGS]
     Gross Margin % = DIVIDE(fact_sales_monthly[GM],fact_sales_monthly[Net Sales])
     2021 vs 2020 = DIVIDE(([NetSales21]-[NetSales20]),[NetSales20],0)
     target 21 = sum(ns_targets_2021[ns_target])
     2021 - target = (fact_sales_monthly[NetSales21]-fact_sales_monthly[target 21])
     2021 - target % = DIVIDE(fact_sales_monthly[2021 - target],fact_sales_monthly[NetSales21],0)
     

### Data Analysis
1. What are the top 10 products based on the percentage increase in their net sales from 2020 to 2021?
     ![q1new](https://github.com/user-attachments/assets/c028466f-1376-4b66-9825-6493be905be9)

 

2. Generate a "Division" report to present the net sales data for 2020 and 2021, along with the growth percentage.
     ![q2](https://github.com/user-attachments/assets/7217c720-aa8c-454c-b1f5-32ef489ccb09)

3. Which products are ranked in the top 5 and bottom 5 in terms of quantity sold?
   ![q3](https://github.com/user-attachments/assets/ef6dcf6f-a6be-47bf-ab49-92e1c30b02b2)

4. What are the new products that Atliq began selling in 2021?
   
   ![q4](https://github.com/user-attachments/assets/c535a796-38aa-4301-812b-deab3ad9a8fe)

6. What are the top 5 countries in terms of net sales in 2021?
   
   ![q5](https://github.com/user-attachments/assets/e34eaea9-ab9f-4b54-bc80-ccbf9a1cd95d)


### Key Insights
