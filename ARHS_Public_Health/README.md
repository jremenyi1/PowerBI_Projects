# Alcohol‑Related Hospital Statistics in Scotland (ARHS)

## Background

Alcohol‑related harm remains a major public health issue in Scotland, with substantial variation between local authority areas. Hospital admission data provide an important lens for examining long‑term trends and geographic inequalities in alcohol‑related harm.

This project analyses **alcohol‑related hospital statistics (ARHS)** using routinely published Scottish health data. The focus is on **how alcohol-related hospitalisation rates change over time**, **how local authorities compare with the national average**, and **where inequalities are most pronounced**, with Dundee City used as a case study.

---

## Aim

The aims of this project are to:

- Clean and standardise a **real‑world public health dataset** in a transparent, reproducible way
- Explore national and local trends in alcohol‑related hospitalisation rates
- Quantify inequalities between council areas and the Scottish average
- Present results clearly using both static and interactive visualisations

The analysis is **descriptive** and does not attempt to infer causality.

---

## Data

The raw dataset, ARHS_byCouncilArea.csv, comes from publicly available Scottish health statistics and reports annual alcohol‑related hospital statistics between 1997 and 2024 and is broken down by:

- Council area (local authority)
- Financial year
- Alcohol‑related condition category
- Measure type (e.g. stays, patients)

Rates are reported as **European Age‑Standardised Rates (EASR) per 100,000 population**, allowing comparison across areas and over time.

Only minimal cleaning is performed in order to preserve the original structure and meaning of the data.

---

## Tools used

This project combines **Python-based analysis** with a **Power BI dashboard**. Python is used for data cleaning, validation, and analytical logic, while Power BI is used for interactive visualisation and stakeholder-facing reporting.

- **Jupyter notebooks** for reproducible workflows
- **Python libraries**
  - **pandas, numpy** for data cleaning and analysis
  - **matplotlib, seaborn** for exploratory figures
- **Power BI** for interactive dashboards
- *(Optional extension)* ArcGIS for spatial visualisation

The two components are deliberately separated but fully aligned: **Power BI only consumes the cleaned dataset produced by the Python pipeline**.
