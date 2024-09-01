# XYZ Electronics Revenue Report.

## Table of Contents.
-  [Dashboard Link](#dashboard-link):![Dashboard.xlsx](https://github.com/user-attachments/files/16574062/Dashboard.xlsx)
-  [Busines Case](#business-case)
-  [Data Sources](#data-sources)
-  [Tools Used](#tools-used)
-  [Data Preparation and Cleaning](#data-preparation-and-cleaning)
-  [Explorative Data Analysis](#explorative-data-analysis)
-  [Tables Creation Through Power Query](#tables-creation-through-power-query)
-  [Data Analysis Expression](#data-analysis-expression)
-  [Results And Findings](#results-and-findings)
-  [Recommendations](#recommendations)

### Business Case.
---

The quarterly General Sales meeting will be holding on Monday morning with all managers in attendance.  As the company's Data Analyst, create a report showing monthly revenue and orders by product category, by Country.

## Planned Solution.
---
### create a Business Report that captures the following Aggregations:
- Total revenue per month.
- Total orders per month.
- Total revenue and Orders overall performance by year.
- Total Revenue and Orders by product category: Performance breakdown for each product category.
- Revenue and orders by country: Performance comparison across different countries.
- % Change in yearly revenue.



![Dashboard.xlsx](https://github.com/user-attachments/files/16574062/Dashboard.xlsx)



### Data Sources


#### Data were scattered in the following sources: 

- Transaction records: The company's transaction data is store in a on premise Microsoft Database containing detail daily transactions information and quantity.

- Product records: Is a "products_data.csv" flat file containing detailed product information and price.

- Stores records: Is a PDF file containing detail location information of all the company's stores.

### Tools Used

SQL Database

Microsoft Excel[Download here](http:microsoft.excel)
- Power Query
- Pivot Table
- Data Model
- DAX (Data Analysis Expresssion)

### Data Preparation and Cleaning.

#### Data Extraction into Power Query Environment for Cleaning.

In the Data preparation phase, Data was Extracted and Clean. Data was extracted from multiple sources into Power Query environment, cleaned by applying the following techniques.

- profiled the data - by analyizing summary statistics of the data
- handling of  null value
- Validating the data
- Check for data constitency
- Checking for Uniqueness and Distinct value count
- Check for data completeness

### Explorative Data Analysis. 

EDA involve exploring the various data to answer the key questions, such as

- What is the overall order trend?
- Which product(s) are top sellers?
- Which country has the highest order per product category?
- Which country has the highest revenue split per product category?

### Tables Creation Through Power Query.
- Sales Table
- Products Table
- Stores Table
- Calendar Table (derived from sales table)

![Pivot Tables.xlsx](https://github.com/user-attachments/files/16574077/Pivot.Tables.xlsx) 

### Data Modeling.

A data model was created using Power Pivot to create a one-to-many relationship of the Fact table(sales) with the Dimension tables(Products, Stores, Calendar) for all Loaded Tables. The data model serving as a single source of truth for analysis.

![Data Model](https://github.com/user-attachments/assets/50e20824-b88e-4fd2-996e-e50f5cb66ac5)

### Data Analysis Expression.

Include some interesting DAX functions to create two columns 
- Column `Total_Order-
-  DAX  <=DISTINCTCOUNT(Sales[Order_Number])>


 - Column`Total_Revenue-
-  DAX <=SUMX(Sales,[Quality]*RELATED(Products[Unit Price USD]))>


Using DAX through "New Measures" in Power Pivot Environment, new columns <Total Order> and <Total Revenue> were created from our Data Model to create the following charts and table

- Total revenue per month chart- filter by country and summation of all country
- Total orders by product category chart- filter by country and summation of all country
- Total revenue by product category chart- filter by year
- Year on year % change in total revenue table
- Total revenue per products- filter by year and summation of years

### Results And Findings.

Revenue exhibited an inconsistent pattern, increasing and decreasing between 2016 and 2020, before declining steadily in 2021. Computers were the most popular product category in terms of both orders and revenue contribution, while TV & Video was the least popular in both aspects. Games and Toys generated the lowest revenue among all product categories.

### Recommendations.
Base on the analysis done, I am recommending the following actions.

- An increase focus on the Computer product category to maintain and potentially increase revenue.
   
- A deeper analysis of the factors contributing to the oscillating revenue pattern and the decline in 2021 should be conducted to identify areas for improvement.

- Invest in marketing and promotion during peak sales to maximize revenue.
 
- Additionally, strategies to boost sales in the TV & Video and Games & Toys categories should be explored to diversify revenue streams.

### Limitations.

- Non availability of a go to personnel or data owners to ask questions regarding data provision and need

### References:
1. Data Wrangling with SQL by [ Raghav Kandarpa & Shivangi Saxena]
2. Gemini AI.









