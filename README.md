# <img src="https://github.com/user-attachments/assets/3d0e1d33-0d58-486a-9ace-65e6b45acfa1" width="5%" height="5%"> Ecommerce Cohort Analysis

<!--<div align="center"> <img src="" width="100%" height="100%"> </div>-->

This repository serves as my documentation for the Ecommerce Cohort Analysis on Customer Retention - Alteryx Project.

It showcases my competancy to work with Alteryx Designer and demonstrates my proficiency in essential tools like **In/Out Tools (Browse, Input Data, Output Data & Text Input), Preparation Tools (Select, Filter, Formula, Sort & Unique), Join Tools (Join, Find Replace & Union) and Documentation Tools (Comment & Tool Container)**.......to be updated.......

The entire project has been implemented using Alteryx Designer 2024.1 (User) (with AMP Engine enabled). The raw data source and data output files have been uploaded to this repository data folder.

---

## Contents:
Please find the sectional links for the project below:
- [Project Objective](#project-objective)
- [Tools used & Methodologies implemented](#tools-used)

---

## Project Objective:
Cohort analysis is a method of grouping customers into cohorts or groups who have undergone a common experience within a specific time frame, such as the date they subscribed to, signed up for or purchased your product. Then you can compare how many customers from each Cohort unit remained active users after one month, two months, three months, etc. This can help you understand the retention patterns and differences between the groupings and their possible causes. In cohort analysis, month 0 usually represents the month when the customer joined or made their first purchase. Cohort Analysis is a valuable technique that enables the extraction of actionable insights related to customer churn, product engagement, product value, and other relevant metrics.

This Alteryx project has been designed with an intent of enhancing e-commerce operations. It has three vital stages: Data Cleanup, Cohort Analysis and Insights generation through which I'll unravel the nuances of online shopping and driving strategic decisions to maximize revenue.

## Tools used:
1. Alteryx Designer - for ETL (Data Import, Data Cleaning, Data Transformation Data Analysis and Data Export) process
2. Datawrapper - for Insight Visuals
3. GitHub - for Documentation

## Skills & Methodologies implemented: .......to be updated.......
1. Data Import - Input Data Tool & Text Imput Tool
2. Data Validation - Select Tool
3. Data Transformation - Join Tool, Find Replace Tool, Unique Tool, Formula Tool & Union Tool
4. Data Export - Output Data Tool
5. Documentation

---

## About the Dataset:

### Data Sources:
The project utilizes the transaction_dataset.csv dataset, which contains detailed information about customer transactions including transaction IDs, product details, customer IDs, dates and order statuses among others. This dataset was sourced from Hicounsellor.com projects titled "Analyzing E-commerce Transactions". This CSV contains 20,000 rows across 13 columns.

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







