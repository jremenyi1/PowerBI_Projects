# Health and Age-group Follow-up Data (2023–2025) Analysis
## Project Overview
In this project, I worked with a messy, real-world–style health and age-group dataset (2023–2025) to practise data cleaning, validation, and dashboard development in Power BI.

This project demonstrates the type of end-to-end work expected in a data analyst role, from preparing unreliable source data to designing user-focused visualisations.

## Data source
- Dataset: Demonstrational Health and Age-group Follow-up Data (2023–2025)
- Variables: Region, Age-group, Gender, Health Status, Year, Count
- File: Clean-Up data task.csv

## Aims
My aim was to transform raw data into clear, interactive dashboards that support high-level overview and trend analysis.

## Dashboard Preview
## Page1 - Visuals

<img width="947" height="540" alt="image" src="https://github.com/user-attachments/assets/18e7af47-a672-4049-889d-7a50468b5c5f" />

## Page2 - Trends

<img width="947" height="540" alt="image" src="https://github.com/user-attachments/assets/1b55886f-7c62-4c73-9567-eb05a2e99657" />
 
## Steps in the Project
The dataset initially contained multiple quality issues, including inconsistent text formatting, mixed data types, duplicate rows, missing values, and extra white spaces.
### Data Cleaning & Preparation (Power Query)
- Removing duplicate records across all columns
- Handling missing values by replacing blanks with "Unknown"
- Trimming leading and trailing white spaces in text fields
- Standardising text case for Region and Gender
- Fixing mixed data types in the Count column by removing text values and converting to whole numbers
- Validating final data types to ensure consistency and analytical accuracy
Once the data was cleaned and validated, it was loaded into Power BI for analysis.
### Dashboard Design & Visualisation
I created a two-page interactive Power BI dashboard, focusing on clarity, consistency, and usability. 
### Page 1 – Visuals
This page provides a high-level overview of the dataset:
- KPI cards showing total records and total population
- Donut chart displaying Health Status distribution
- Stacked bar chart comparing Age Groups by Health Status
- Dropdown slicers for Year, Region, and Gender
### Page 2 – Trends
This page supports deeper exploratory analysis:
- Line chart showing Health Status trends over time
- Clustered bar chart comparing Regions by Health Status
- Slicers for Health Status, Region, and Year
All visuals were formatted consistently to improve readability and user experience.
## Files in This Repository
- Original dataset - Clean-Up data task.csv
- Power BI dashboard file - Health_Age_Analysis.pbix

