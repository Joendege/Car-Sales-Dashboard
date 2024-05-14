# Car Sales Dashboard

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Recommedations](#recommedations)
- [Results and Findings](#results-and-findings)
- [References](#references)

### Project Overview
---
This data analysis project aims to provide insights for the car sales performance for a period of 2 years, while comparing the sales revenue, car sold and average price for the two years. By analyzing various aspects of the car sales data, we will indentify trends, make data driven recommedations and gain a deeper understanding of the company performance.


![car_sales](https://github.com/Joendege/Car-Sales-Dashboard/assets/123901910/8f9e1f07-1bdf-4087-859c-603d0b81f7d0)

### Data Sources
---
Car Sales Data: The primary data source used for this analysis is the "Car Sales Data.xlsx" file, containing each record of each car sale that was made for the two years by the company.

### Tools
---
- Power Query- Data Cleaning and Preparation
- Power Pivot- Performing advanced data analysis using DAX Formulas
- Power BI- Report Creating and Visualizations

### Data Cleaning and Preparation
---
In this phase i performed the following tasks:
1. Data loading and Inspection
2. Genarating Date Tables
3. Data Cleaning and Modelling
4. Data Formatting

### Exploratory Data Analysis
---
EDA involved exploring the sales data to answer the following questions:
- What is the YTD sales revenue, average price and car sold?
- How the sales compare in diffent weeks per year?
- What are top sellors based on car body style and color?
- How are sales based on dealer region?
- Which are the best sellors based on company?


### Data Analysis
---
```DAX
Max Point = IF(MAXX(ALLSELECTED('Calender Table'[Week]), [Total Sales]) = [Total Sales], MAXX(ALLSELECTED('Calender Table'[Week]), [Total Sales]), BLANK())
```
```DAX
YTD Total Sales = TOTALYTD(SUM(car_data[Price ($)]), 'Calender Table'[Date])
```
```DAX
PYTD Total Sales = CALCULATE(SUM(car_data[Price ($)]), SAMEPERIODLASTYEAR('Calender Table'[Date]))
```
```DAX
YoY Growth Sales = [Sales Difference]/ [PYTD Total Sales]
```
```DAX
MTD Total Sales = TOTALMTD(SUM(car_data[Price ($)]), 'Calender Table'[Date])
```
```DAX
Car Sold Diff Color = IF([Car Sold Difference] > 0, "Green", "Red")
```

### Recommedations
---
Based on the analysis we recommed the following actions:
- Invest in marketing and brand campaings for the Hatchback body style to increase sales
- Impliment customer segmentation to target the hatchback customers
- Conduct marketing and brand campaings in regions where dealer sales are low.


### Results and Findings
---
The analysis results are summarized as follows:
- The company sales and car sold increased in comparison to the previous year.
- Auto engine transmission cars are highest selling in comparision to manual cars.
- Based on body style SUV contributes to highest sales

### References
---
1. [DAX Functions](https://learn.microsoft.com/en-us/dax/time-function-dax)
2. [Stack Overflow](https://stackoverflow.com/)
