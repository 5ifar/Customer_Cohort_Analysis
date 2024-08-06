# <img src="https://github.com/user-attachments/assets/3d0e1d33-0d58-486a-9ace-65e6b45acfa1" width="5%" height="5%"> Ecommerce Cohort Analysis

<!--<div align="center"> <img src="" width="100%" height="100%"> </div>-->

This repository serves as my documentation for the Ecommerce Cohort Analysis on Customer Retention - Alteryx Project.

It showcases my competancy to work with Alteryx Designer and demonstrates my proficiency in essential tools like **In/Out Tools (Browse, Input Data, Output Data), Preparation Tools (Auto Field Tool, Data Cleansing Tool, Filter Tool, Formula Tool, Multi-Field Tool, Sample Tool, Select Tool, Sort Tool, Unique Tool), Join Tools (Join, Append Fields & Union), Transform Tools (Cross-Tab Tool, Summarize Tool), Parse Tools (DateTime Tool, Text to Columns Tool) and Documentation Tools (Comment & Tool Container).**

The entire project has been implemented using Alteryx Designer 2024.1 (User) (with AMP Engine enabled). The raw data source and data output files have been uploaded to this repository data folder.

---

## Contents:
Please find the sectional links for the project below:
- [Project Objective](#project-objective)
- [Tools used & Methodologies implemented](#tools-used)
- [About the Dataset](#about-the-dataset)
  - [Data Sources](#data-sources)
  - [Data Dictionary](#data-dictionary)
  - [Data Integrity](#data-integrity)
- [Project Implementation](#project-implementation)
  - [Phase 1 - Data Cleaning](#phase-1---data-cleaning)
  - [Phase 2 - Cohort Analysis](#phase-2---cohort-analysis)
  - [Phase 3 - Key Business Insights Generation](#phase-3---key-business-insights-generation)
- [Workflow Layout](#workflow-layout)
- [Data Outputs](#data-outputs)

---

## Project Objective:
Cohort analysis is a method of grouping customers into cohorts or groups who have undergone a common experience within a specific time frame, such as the date they subscribed to, signed up for or purchased your product. Then you can compare how many customers from each Cohort unit remained active users after one month, two months, three months, etc. This can help you understand the retention patterns and differences between the groupings and their possible causes. In cohort analysis, month 0 usually represents the month when the customer joined or made their first purchase. Cohort Analysis is a valuable technique that enables the extraction of actionable insights related to customer churn, product engagement, product value, and other relevant metrics.

This Alteryx project has been designed with an intent of enhancing e-commerce operations. It has three vital stages: Data Cleanup, Cohort Analysis and Insights generation through which I'll unravel the nuances of online shopping and driving strategic decisions to maximize revenue.

## Tools used:
1. Alteryx Designer - for ETL (Data Import, Data Cleaning, Data Transformation Data Analysis and Data Export) process
2. Datawrapper - for Insight Visuals
3. GitHub - for Documentation

## Skills & Methodologies implemented:
In this project, I leveraged the skills and knowledge acquired during the Alteryx Designer Core Certification and the pursuit of 4 other micro-credentials. This allowed me to harness a robust set of Alteryx tools, putting them to work in a cohesive workflow. Throughout this project, I harnessed the full potential of Alteryx, seamlessly executing all phases and leveraging a range of powerful tools from each tool palette:

1. Data Import/Export - In/Out Tools: Input Tool, Output Tool, Browse Tool
2. Data Preparation - Preparation Tools: Auto Field Tool, Data Cleansing Tool, Filter Tool, Formula Tool, Multi-Field Tool, Sample Tool, Select Tool, Sort Tool, Unique Tool
3. Data Transformation - Join Tools: Append Fields Tool, Join Tool & Transform Tools: Cross-Tab Tool, Summarize Tool & Parse Tools: DateTime Tool, Text to Columns Tool
4. Documentation - Documentation Tools: Comment, Tool Container

---

## About the Dataset:

### Data Sources:
The project utilizes the transaction_dataset.csv dataset, which contains detailed information about customer transactions including transaction IDs, product details, customer IDs, dates and order statuses among others. This dataset was sourced from Hicounsellor.com projects titled "Analyzing E-commerce Transactions". This CSV contains 20,000 rows across 13 columns.

[Link to Data Source](https://github.com/5ifar/Ecommerce_Cohort_Analysis/tree/main/Data/Data%20Source)

### Data Dictionary:
The dataset provides the following key attributes:

|Column name|Data type|Description|
|-|-|-|
|transaction_id|Double|Unique Transaction ID|
|product_id|Double|Unique Product ID|
|customer_id|Double|Unique Customer ID|
|transaction_date|Date|Date of Transaction|
|online_order|Bool|If Order was placed Online (either True/False)|
|order_status|V_String|Current Order Status (Approved/Unapproved)|
|brand|V_String|Product Brand|
|product_line|V_String|Line of Product|
|product_class|V_String|Class of Product|
|product_size|V_String|Size of Product|
|list_price|Double|List Price of Product|
|standard_cost|Double|Standard Cost of Product|
|product_first_sold_date|Date|Date Product was first sold|

## Data Integrity:
ROCCC Evaluation:
- Reliability: MED - The raw dataset is created and updated by Hicounsellor. It has a single file.
- Originality: HIGH - First party provider (Hicounsellor)
- Comprehensiveness: MED - Total 20000 records were provided. Dataset contains multiple dimension parameters for Products as well as Order transaction data.
- Current: LOW - Dataset contains 2017 data i.e almost 7 years old. So its not relevant. Any trends observed and insights gained need to be comprehended as a proof of concept.
- Citation: LOW - No official citation/reference available.

---

## Project Implementation:
This Alteryx workflow is designed to perform comprehensive analysis on customer transactions using the provided dataset. The project encompasses three main phases: 1.Data Cleaning 2.Cohort Analysis 3.Business Insights Generation.

### Phase 1 - Data Cleaning:

1. Imported the data from the transaction_dataset.csv file using the Input Data tool. Checked for initial data integrity using temporary Browse tool.
2. Ensured correct data types that were compatible for analysis using Auto Field tool. Changes: `[tr_id]/[c_id]` → Int16, `[p_id]` → Byte, `[online_order]` → Bool, `[tr_date]/[order_status]/[brand]/[product_line]/[product_class]/[product_size]` → String, `[list_price]/[standard_cost]/[product_first_sold_date]` → double
3. Split `[tr_date]` String field based on Space delimiter to dissolve the existing `‘dd-mm-yyyy hh:mm’` String format into 2 separate fields: `[tr_date1] ‘dd-mm-yyyy’` and `[tr_date2] ‘hh:mm’` using the Text to Columns Parse tool. Then used the DateTime Parse tool to convert the `[tr_date1]` String field with `‘dd-mm-yyyy’` format into `[transaction_date]` Date field with standard `‘yyyy-mm-dd’` format.
4. Selected & Renamed column names to enhance clarity using Select tool. Changes: `[tr_id] → [transaction_id], [p_id] → [product_id], [c_id] → [customer_id]`, `[tr_date]/[tr_date1]/[tr_date2]` → Fields Removed
5. Filtered out Null values for `[product_class]` and `[product_size]` fields using Custom Filter: `!IsNull([product_class]) OR !IsNull([product_size])`. Checked for final data integrity using temporary Browse tool. Although removing these null values do not affect my Cohort Analysis, it has been followed as a data cleaning principle.
6. Export the data to Cleaned Transactions Dataset.xlsx file using the Output tool. Encase all the above select tools in a Tool Container titled ‘Phase 1: Data Cleaning’.

### Phase 2 - Cohort Analysis:
This phase involved the following steps: **Customer Segmentation:** Grouped customers into cohorts based on their transaction behavior, **Cohort Metrics:** Calculated key metrics (E.g. Cohort Month, Cohort Index & Retention Rate) for each cohort, **Tabular Representation:** Generated Cohort Retention rate to aid in cohort comparison.

1. Imported the dataset from the cleaned_transaction_dataset.xlsx file using the Input Data tool.
2. Filtered for all the transactions where the `[order_status]` field is Approved using Filter tool since, unapproved orders data is not relevant for a Customer Cohort Analysis.
3. Isolate the `[customer_id]` & `[transaction_date]` fields using the Select tool.
4. Extract and Parse to Number the year and month portion of `[transaction_date]` field in `‘yyyymm’` format using Formula tool with formula: `[transaction_month_YM] = Tonumber(DateTimeFormat([transaction_date], "%Y%m"))`
5. Find the first month of transaction in the dataset using Summarize tool by calculating the min value of `[transaction_month_YM]` field as `[transaction_start_month_YM]` field.
6. Append the `[transaction_start_month_YM]` field to the dataset using the Append tool.
7. Calculate the difference between the current transaction month and first transaction month as the transaction month index using the Formula tool with formula: `[transaction_month_index] = Tonumber([transaction_month_YM]) - ToNumber([transaction_start_month_YM])` formatted as Int16 datatype. The transaction month index parameter represents the count of intervals of the current transaction month since the first transaction month.
8. Group the dataset by `[customer_id]` field and calculate the minimum `[transaction_month_index]` field as `[cohort_month]` field using the Summarize tool.
9. Encase all the above 2 → 8 tools in a Tool Container titled ‘Task: Filter by Approved orders and Calculate Month Index & Cohort Month’.
10. Join the `[cohort_month]` field with the dataset based on the `[customer_id]` field using the Join tool.
11. Calculate the difference between the transaction month index value and the cohort month as the cohort index using the Formula tool with formula: `[cohort_index] = [transaction_month_index] - [cohort_month]`

    Cohort Index is an integer representation of the number of months that has passed since a customer's first transaction.
12. Encase all the above 10 → 11 tools in a Tool Container titled ‘Task: Assign Cohort Index’.
13. Group the dataset by `[customer_id]`, `[cohort_month]` and `[cohort_index]` fields and Count the records as `[customer_count]` field using the Summarize tool.
14. Pivot the dataset using Cross Tab tool by grouping with `[cohort_month]` field, setting `[cohort_index]` as column headers and setting sum aggregation of `[customer_count]` field as values in the table.

    The resulting table provides insight on the number of customers who have continued to use a product or service over time, which can be further analyzed through the calculation of retention rates.
15. Sort the dataset based on `[cohort_month]` field in ascending order.
16. Encase all the above 13 → 15 tools in a Tool Container titled ‘Task: Create Cohort Data Pivot Table’.
17. Replace existing null values in the dataset with 0 value using the Data Cleansing tool.
18. Convert all values in the dataset into percentages by taking the first column values as base using the Multi-Field Formula tool with formula: `([CurrentField*]* / [0]) * 100` and formatting the output type as Fixed decimal with 19.2 size. These values are the Customer Retention Rates for each cohort.
19. Encase all the above 17 → 18 tools in a Tool Container titled ‘Task: Cohort Retention Rate Table’.
20. Encase the entire workflow above in a Master Tool Container titled ‘Phase 2: Cohort Analysis’. Export the data to Cohort Analysis Data.xlsx file using the Output tool.

### Phase 3 - Key Business Insights Generation:
This final phase encompasses building workflows to derive the following insights:
- **Distinct Brands**: Identified unique brands available in the dataset.
- **Total Sales Amount by Brand**: Calculated the total sales amount for each brand.
- **Unique Customers**: Counted the number of unique customers who made transactions.
- **Approved vs. Unapproved Orders**: Quantified approved and unapproved transactions.
- **Average List Price by Product Line**: Listed top product lines with the highest average list price.
- **Top 5 Profitable Brands**: Identified brands with the highest profit margin.
- **Top 5 Products with Highest Profit Margin**: Identified the top 5 products with the highest profit margin.
- **Customer Spending Analysis**: Calculated three metrics for each customer: Total number of transactions, Total amount spent & Average profit per transaction
- **Top 5 Product Lines by Revenue Contribution**: Identified product lines with the highest total revenue contribution.
- **Customers Engaged with Entire Product Range**: Identified customers who made transactions in all distinct product lines.

---

## Workflow Layout:

<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Ecommerce%20Cohort%20Analysis%20Project%20Workflow.jpg" width="100%" height="100%"> </div>

---

## Data Outputs:
[Link to Data Outputs](https://github.com/5ifar/Ecommerce_Cohort_Analysis/tree/main/Data/Data%20Outputs)

---
