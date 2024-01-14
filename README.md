# Customer Retention Analysis- PWC
## Introduction
This project aims to create a Power BI dashboard for retention managers that reflects Key Performance Indicators (KPIs).
## Data Preparation
The dataset is stored in an Excel file containing one table. The data was loaded into Power BI Desktop and transformed in the Power query editor.  
## Data Process
- Validated column data types
- Added a new column using the following formula:
-     Churned = IF('01 Churn-Dataset'[Churn] = "Yes",1,0) 
- Created a new table for measures.
## Data Analysis
The following measures were created using DAX:
-     Total Customers = COUNT('01 Churn-Dataset'[customerID]) 
-     Total Churned Customers = SUM('01 Churn-Dataset'[Churned])
-     Female Customers = CALCULATE(COUNT('01 Churn-Dataset'[gender]), FILTER('01 Churn-Dataset', '01 Churn-Dataset'[gender] = "Female"))
-     Male Customers = CALCULATE(COUNT('01 Churn-Dataset'[gender]), FILTER('01 Churn-Dataset', '01 Churn-Dataset'[gender] = "Male"))
-     Monthly Charges = SUM('01 Churn-Dataset'[MonthlyCharges])
-     Independents = CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), FILTER('01 Churn-Dataset', '01 Churn-Dataset'[Dependents] = "No"))  
-     Weekly charges = SUM('01 Churn-Dataset'[TotalCharges])
-     Dependents = CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), FILTER('01 Churn-Dataset', '01 Churn-Dataset'[Dependents] = "Yes"))

## Data Visualization
![dashboard](https://github.com/SorathF/PWC_Customer_Retention/blob/11e0f0f177895551923a84aba1eb9e4fd73a00e6/Customer%20Retention.png)
