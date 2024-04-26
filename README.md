# Sales Insights analysis

## Table of Contents

  - [Project Overview](#project-overview)
  - [Data Sources](#data-sources)
  - [Tools](#tools)
  - [Data Cleaning/Preparation](#data-cleaningpreparation)
  - [Exploratory Data Analysis](#exploratory-data-analysis)
  - [Data Analysis](#data-analysis)
  - [Analysis Findings/Results](#analysis-findingsresults)
  - [Recommendations](#recommendations)
  - [Limitations](#limitations)
  - [References](#references)

### Project Overview

The objective of this project is to analyze the sales data of a company that supplies hardware equipment to different stores/customers across India. The main goals are to determine which region yields the highest profits and to examine the sales trends over the years.
This data analysis project is centered around exploring various aspects of sales data to uncover insights, detect trends, and identify patterns. The findings from this analysis will inform data-driven recommendations for the organization.

### Data Sources

The data for this project has been sourced from Code Basics, an online data analysis/science teaching platform. The dataset is stored in a MySQL file, which is included above as () for reference.

### Tools

- SQL server - Data analysis
- Power Query and Power BI - Data cleaning, Data transformation, Visualizations and Interactive dashboards

### Data cleaning/Preparation

In the first stage, below are taken care:
1. Downloaded and inspected the quality of data.
2. Data is cleaned and formatted for accuracy and consistency.

### Exploratory Data Analysis

In this process, the following questions need to be answered:

1. What is the contribution of revenue?
2. What is the contribution of profit?
3. Who are the top customers based on revenue and profit margin?
4. What is the profit margin in each zone?

### Data Analysis

Data is analysed in SQL using different queries to know the insights of the data like how particular market is doing or how the sales in a certain year look like.
Analysis is viewed through SQL, examples as below:

```sql
SELECT count(*)
FROM sales.transactions
JOIN sales.date
ON sales.transactions.order_date = sales.date.date
WHERE year = 2020;
```
```sql
SELECT SUM(sales.transactions.sales_amount)
FROM sales.transactions
JOIN sales.date
ON sales.transactions.order_date = sales.date.date
WHERE sales.date.year = 2020 and sales.transactions.market_code = "Mark001";
```
```sql
SELECT *
FROM sales.transactions
WHERE sales_amount <= 0;
```

### Analysis Findings/Results

Note: The currency used in the analysis is represented in Indian Rupees.

1. Here are the findings for the revenue contribution and profit contribution of all markets, customers, and products in 2020. Additionally, the revenue trend for the year 2020 is illustrated.
   Despite the high revenue contribution of the Delhi market, the Mumbai market leads in profit contribution. Furthermore, the Bhubaneshwar market exhibits a higher profit margin.




2. a) A bar chart illustrating the profit margin of each zone, indicating that the South zone has the highest profit margin while the North zone has the lowest.
   b) A table displaying the list of customers, allowing for the identification of both top and bottom customers based on revenue.
  c) A revenue trend graph comparing profits from the years 2020 and its previous year (2019), indicating a decrease in sales profits from 2019 to 2020.

  



### Recommendations

1. It is advisable to monitor and address the discrepancy between revenue and profit in markets like Delhi, where the revenue significantly outweighs the profit. Taking corrective action in these markets could help improve profitability.
2. Implementing a strategy to identify and reward top customers with special offers or discounts can enhance customer retention and foster long-term relationships with key clients.
3. Given the declining profits, it is essential to investigate the underlying factors that may have contributed to this trend, such as changes in sales strategies or shifts in customer relationships. Identifying and addressing these changes can help steer the company back towards profitability.

### Limitations

1. Certain foreign markets have been excluded from the analysis as their contribution to sales insights is minimal.
2. The dataset contains product codes, but there is no accompanying data for product names, making it challenging to identify the top-selling products. Additionally, some product codes are missing, yet they are still generating significant revenue.
3. The sales data includes transactions denominated in USD, which have been converted to Indian Rupees. However, there is a need for more precise conversion to determine the exact value of the Indian Rupees corresponding to the specific date or time of the transactions.

### References

1. Code Basics online platform [Codebasics website](https://codebasics.io/))
2. MySQL

