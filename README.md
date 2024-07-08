# Customer Segmentation for an Automobile Bike Company

## Goal of the project
The objective of this project is to perform Customer Segmentation Analysis for an automobile bike company using an RFM (Recency, Frequency, Monetary) model. This behavior-based methodology classifies customers into segments based on their past purchase behaviors. The analysis identifies 11 distinct customer groups to target specific segments and boost sales revenue. A Sales Dashboard for Customer Segmentation was created using Tableau, with data quality assessment and analysis conducted in Excel. A <b>Sales Dashboard for Customer Segmentation</b> has been created using <b>Tableau</b>, with data quality assessment.


## Tableau Dashboard
The Sales Dashboard for Customer Segmentation is accessible [here](https://public.tableau.com/views/SalesDashboard_17201045476280/RFMDashboard?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).<br>
<img src="data%20visualization/Sales%20Dashboard.gif" height="500" align="middle"><br>


## Analysis Approach
### 1. Data Quality Assessment and Data Cleaning
The initial step to derive valuable insights from the data involved data preparation, quality assessment, and data cleaning. Once the data was cleaned, exploratory data analysis was performed to identify customer purchasing behaviors and generate insights.

During the data cleaning phase, the quality of the following datasets was evaluated. After assessing data quality, the following issues were identified and addressed accordingly:
- <b>CustomerDemographics.xlsx</b> :
  - One irrelevant column was found and removed from the dataset.
  - Five columns contained missing values. Depending on the volume of missing data, either the records were removed or appropriate values were imputed.
  - The gender column lacked standardization. The data was standardized to eliminate inconsistencies.
  - The Date of Birth column was transformed to create new 'Age' and 'Age Group' features to check for discrepancies in age distribution. One outlier was identified and removed.
  - Checked for duplicate records; none were found.
- <b>NewCustomerList.xlsx</b> :
  - Five irrelevant columns were found and removed.
  - Four columns had missing values. Records with missing values were either dropped or imputed based on the volume of missing data.
  - The Date of Birth column was used to create 'Age' and 'Age Group' features to check for age distribution discrepancies.
  - No data inconsistencies were found.
  - Checked for duplicate records; none were found.
- <b>Transaction_data.xlsx </b>:
  - The product_first_sold_date column was not in datetime format. It was converted from int64 to datetime.
  - Seven columns had missing values. Depending on the volume, records were either dropped or imputed.
  - A new 'Profit' feature was created as the difference between the list price and standard price.
  - No data inconsistencies were found.
  - Checked for duplicate records; none were found.
- <b>CustomerAddress.xlsx</b> :
  - The states column lacked standardization. It was standardized to remove inconsistencies.
  - Some customer IDs from the Customer Demographics table were missing in the Address table.

### 2. Exploratory Data Analysis on Customer Segments
After cleaning the data, exploratory analysis was conducted, revealing the following insights:
- <b>New vs Old Customers Age Distribution</b><br> 
  - Most new and old customers are aged between 40-49.
  - The fewest customers are in the under-20 and over-80 age groups for both new and old customers.
  - The company is popular among new customers aged 20-29 and 40-49.
  - A significant drop in customers is observed in the 30-39 age group among new customers.<br>
  <table>
  <tr>
    <td><b>Old Customers by Age Distribution</b></td>
    <td><b>New Customers by Age Distribution</b></td>
  </tr>
  <tr>
    <td><img src="images/Old Customers Age Distribution.png" height="400" align="middle"></td>
    <td><img src="images/New Customers Age Distribution.png" height="400" align="middle"></td>
  </tr>
  </table>
  
- <b>Bike purchases over last 3 years by Gender</b><br> 
  - Most bike purchases over the last three years were made by females, accounting for approximately 51% of the purchases compared to 49% by males.
  - Numerically, female purchases exceeded male purchases by 10,000.
  <img src="images/Female vs Male Bike Purchases.png" height="400" align="middle">
  
- <b>New vs Old Customers Job Industry Distribution</b><br> 
  - Most new customers come from the Manufacturing and Financial Services sectors (approximately 20% each).
  - The fewest customers are from the Agriculture and Telecom sectors (approximately 3% each).
  - Similar trends are observed among old customers.<br>
  <table>
  <tr>
    <td><b>Old Customers by Job Industry</b></td>
    <td><b>New Customers by Job Industry</b></td>
  </tr>
  <tr>
    <td><img src="images/Old Customers Job Industry.png" height="400" align="middle"></td>
    <td><img src="images/New Customers Job Industry.png" height="400" align="middle"></td>
  </tr>
  </table>

- <b>Wealth Segmentation by Age Category</b><br> 
  - Across all age categories, the majority of customers belong to the 'Mass Customer' segment.
  - The next largest group is 'High Net Worth' customers.
  - In the 40-49 age group, the 'Affluent' segment outperforms the 'High Net Worth' segment in terms of customer numbers.<br>
  <table>
  <tr>
    <td><b>Old Customers Wealth by Age Group</b></td>
    <td><b>New Customers Wealth by Age Group</b></td>
  </tr>
  <tr>
    <td><img src="images/Old Customers Wealth Segment.png" height="400" align="middle"></td>
    <td><img src="images/New Customer Wealth Segment.png" height="400" align="middle"></td>
  </tr>
  </table>

- <b>Cars owned by States</b><br> 
  - New South Wales has the highest number of people who do not own a car.
  - In Victoria, the proportions are fairly even.
  - In Queensland, the number of people owning a car exceeds those who do not.
  <img src="images/Car Owners by State.png" height="400" align="middle">


### 3. RFM Analysis and Customer Segmentation
In this stage, customer segmentation was performed using an RFM Model. RFM (Recency, Frequency, Monetary) analysis groups customers based on their previous purchase transactions.

In this analysis the customer segment was divided into 11 groups. The groups being : 
- Platinum Customers
- Very Loyal Customers
- Recent Customers
- Potential Customers
- Lost Customers
- Losing Customers
- Late Bloomer
- High Risk Customers
- Evasive Customers
- Becoming Loyal
- Almost lost Customers

The current distribution of customer segments in the automobile business is illustrated below:
<img src="images/Customer Segment Distribution.png" height="400" align="middle">

### 4. RFM Analysis: Scatter Plots
#### Recency vs Monetary :
The visualization indicates that recent customers have made more purchases and generated more revenue compared to those who visited a while ago.<br>
<img src="images/Recency vs Monetary.png" height="400" align="middle"><br>

#### Frequency vs Monetary : 
The visualization shows that customers in the Platinum, Very Loyal, and Becoming Loyal segments have higher frequency and generate greater revenue.<br>
<img src="images/Frequency vs Monetary.png" height="400" align="middle"><br>

## Datasets Used
The datasets utilized in this analysis include:
- __Raw_data.xlsx__: This file contains the following sheets:
  -  __Transactions_data.xlsx__: Contains transaction data of customers across different states in Australia.
  -  __NewCustomerList.xlsx__: Includes new customers who recently visited the automobile bike company.
  -  __CustomerDemographic.xlsx__: Provides comprehensive details of customer demographics.
  -  __CustomerAddress.xlsx__: Contains customer addresses.


## Tools and Technologies used
The tools used in this project include:
- __Excel__ - Utilized for data quality assessment, data cleaning, and preliminary analysis.
- __Tableau__ - This business intelligence tool was used to explore data, create charts, graphs, and visualizations, and develop a Sales Dashboard for Customer Segmentation. The Tableau Sales Dashboard can be found [here](https://public.tableau.com/views/SalesDashboard_17201045476280/RFMDashboard?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)


## Built With
- Excel, Tableau

