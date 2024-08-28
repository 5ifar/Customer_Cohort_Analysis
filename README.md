# <img src="https://github.com/user-attachments/assets/3d0e1d33-0d58-486a-9ace-65e6b45acfa1" width="5%" height="5%"> Customer Cohort Analysis

<!--<div align="center"> <img src="" width="100%" height="100%"> </div>-->

This repository serves as my documentation for the Customer Cohort Analysis on Customer Retention - Alteryx Project.

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
- [Workflow Layout](#workflow-layout)
- [Cohort Analysis Insights](#cohort-analysis-insights)
- [Key Business Insights](#key-business-insights)

---

## Project Objective:
Cohort analysis is a method of grouping customers into cohorts or groups who have undergone a common experience within a specific time frame, such as the date they subscribed to, signed up for or purchased your product. Then you can compare how many customers from each Cohort unit remained active users after one month, two months, three months, etc. This can help you understand the retention patterns and differences between the groupings and their possible causes. In cohort analysis, month 0 usually represents the month when the customer joined or made their first purchase. Cohort Analysis is a valuable technique that enables the extraction of actionable insights related to customer churn, product engagement, product value, and other relevant metrics.

This project deals with a specific type of cohort analysis called Acquisition cohort analysis. It divides users into cohorts based on acquisition events. For the scope of this project the acquisition event is defined as the customers first transaction month. This kind of analysis allows organizations to identify long-term retention patterns for each cohort and compare the effectiveness of various retention strategies over time.

This Alteryx project has been designed with an intent of enhancing e-commerce operations. It has three vital stages: Data Cleanup, Cohort Analysis and Insights generation through which I'll unravel the nuances of online shopping and driving strategic decisions to maximize revenue.

## Tools used:
1. Alteryx Designer - for ETL (Data Import, Data Cleaning, Data Transformation Data Analysis and Data Export) process
2. Datawrapper - for Insight Visuals
3. GitHub - for Documentation

## Skills & Methodologies implemented:
In this project, I leveraged the skills and knowledge acquired during the Alteryx Designer Core Certification and the pursuit of 4 other micro-credentials. This allowed me to harness a robust set of Alteryx tools, putting them to work in a cohesive workflow. Throughout this project, I harnessed the full potential of Alteryx, seamlessly executing all phases and leveraging a range of powerful tools from each tool palette:

1. Data Import/Export - **In/Out Tools: Input Tool, Output Tool, Browse Tool**
2. Data Preparation - **Preparation Tools: Auto Field Tool, Data Cleansing Tool, Filter Tool, Formula Tool, Multi-Field Tool, Sample Tool, Select Tool, Sort Tool, Unique Tool**
3. Data Transformation - **Join Tools: Append Fields Tool, Join Tool & Transform Tools: Cross-Tab Tool, Summarize Tool & Parse Tools: DateTime Tool, Text to Columns Tool**
4. Documentation - **Reporting Tools: Basic Table, Documentation Tools: Comment, Tool Container**

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
Please find the documentation links for the project phase-wise implementation below:
- [Phase 1 - Data Cleaning & Transformation](https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Project%20Implementation/Documentation.md#phase-1---data-cleaning--transformation)
- [Phase 2 - Cohort Analysis](https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Project%20Implementation/Documentation.md#phase-2---cohort-analysis)
- [Phase 3 - Key Business Insights Generation](https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Project%20Implementation/Documentation.md#phase-3---key-business-insights-generation)

---

## Workflow Layout:

### I. Data Cleaning & Cohort Analysis Workflow:
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/ECA%20Project%20-%20Data%20Cleaning%20%26%20Cohort%20Analysis%20Workflow.png" width="100%" height="100%"> </div>

### II. Business Insights Workflow:
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/ECA%20Project%20-%20Business%20Insights%20Workflow.png" width="100%" height="100%"> </div>

---

## Cohort Analysis Insights:
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Cohort%20Analysis%20Data%20Matrix.PNG" width="100%" height="100%"> </div>

**Horizontal Axis Analysis:** April (47.11 %) and July 2017 (44.79 %) Cohorts have the highest customer retention rate in the 90 - 120 elapsed days period.

**Vertical Axis Analysis:** For 90 days period, April (47.11 %), July (43.75 %) and August 2017 (43.94 %) Cohorts display the highest retention. For 120 days period, April (44.57 %) and July 2017 (44.79 %) Cohorts display the highest retention. For 180 days period, April (40.88 %) and June 2017 (43.42 %) Cohorts display the highest retention.

**Diagonal Axis Analysis:** For the month of December 2017, the June Cohort displays the highest customer retention rate of 43.42 % and the August Cohort displays the lowest customer retention rate of 19.70 %.

---

## Key Business Insights:

### 1. & 2. Distinct Brands & Total Sales Amount by Brand: Identified unique brands available in the dataset and Calculated the total sales amount for each brand.
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%201%2C2%20Data.png" width="50%" height="50%"> </div> 
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%201%2C2%20Visual.png" width="100%" height="100%"> </div>

### 3. Unique Customers: Counted the number of unique customers who made transactions.
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%203%20Data.png" width="50%" height="50%"> </div>

### 4. Approved vs. Unapproved Orders: Quantified approved and unapproved transactions.
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%204%20Data.png" width="50%" height="50%"> </div>
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%204%20Visual.png" width="100%" height="100%"> </div>

### 5. Average List Price by Product Line: Listed product lines with their average list price.
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%205%20Data.png" width="50%" height="50%"> </div>
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%205%20Visual.png" width="100%" height="100%"> </div>

### 6. Top 5 Profitable Brands: Identified top 5 brands with the highest profit margin.
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%206%20Data.png" width="50%" height="50%"> </div>
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%206%20Visual.png" width="100%" height="100%"> </div>

### 7. Top 5 Profitable Products: Identified top 5 products with the highest profit margin.
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%207%20Data.png" width="50%" height="50%"> </div>
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%207%20Visual.png" width="100%" height="100%"> </div>

### 8. High Markup Products: Listed the products where the list_price is greater than twice the standard_cost.
This is a sample of output. The entire data can be viewed here: [High Markup Products.yxdb](https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Dataset/Processed%20Data/High%20markup%20Products.yxdb)
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%208%20Data%20Preview.png" width="50%" height="50%"> </div>
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%208%20Visual.png" width="50%" height="50%"> </div>

### 9. Product Lines by Revenue Contribution: Identified total revenue contribution for all product lines.
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%209%20Data.png" width="50%" height="50%"> </div>
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%209%20Visual.png" width="100%" height="100%"> </div>

### 10. Customer Spending Analysis: Calculated three metrics for each customer: Total number of transactions, Total amount spent & Average profit per transaction.
This is a sample of output. The entire data can be viewed here: [Customer Spending Analysis.yxdb](https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Dataset/Processed%20Data/Customer%20Spending%20Analysis.yxdb)
<div align="center"> <img src="https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Assets/Business%20Insights%20Files/Insight%2010%20Data%20Preview.png" width="50%" height="50%"> </div>

### 11. High Engagement Customers: Identified customers who made transactions in all distinct product lines within the entire Product Range.
A total of 69 customers were identified as High Engagement Customers. Their customer_id data can be viewed here: [High Engagement Customers.yxdb](https://github.com/5ifar/Ecommerce_Cohort_Analysis/blob/main/Dataset/Processed%20Data/High%20Engagement%20Customers.yxdb)

---
