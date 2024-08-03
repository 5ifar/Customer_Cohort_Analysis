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




