# Alcohol‑Related Hospital Statistics in Scotland (ARHS)

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?logo=python&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)
![Public Health](https://img.shields.io/badge/Domain-Public%20Health-2E8B57)

## At a glance

This project analyses alcohol-related hospital stay rates across Scottish council areas.
It combines reproducible Python analysis with an interactive Power BI dashboard.

**Tools:** Python, pandas, Jupyter, Power BI, DAX

**Focus:** Time trends, local–national comparison, health inequalities

**Outputs:** Clean dataset, analysis notebooks, interactive dashboard

## Project outputs

**Quick links:**

[![View Power BI Dashboard](https://img.shields.io/badge/Power%20BI-Interactive%20Dashboard-yellow)](https://app.powerbi.com/view?r=eyJrIjoiM2UxNGM3YjItNDBmNS00NGI4LTg5MTMtZTNlMDJjZmVlOGVkIiwidCI6IjZjODBiOWI3LTM4ZTktNDNmOS05YTllLWM3NTVhNTg5MzllNyJ9)

[![Python Notebooks](https://img.shields.io/badge/Open-Python%20Notebooks-3776AB?logo=python&logoColor=white)](./notebooks)

[![Clean Dataset](https://img.shields.io/badge/View-Cleaned%20Dataset-4CAF50)](./data/processed/ARHS_byCouncilArea_clean.csv)

---

## Background

Alcohol-related hospital admissions remain a major public health issue in Scotland. Rates vary over time and differ widely between council areas. Understanding these patterns is essential for identifying persistent inequalities and targeting prevention efforts.

This project combines Python and Power BI. Python is used to clean the data and validate trends. Power BI is used to present the same findings in an interactive and accessible way. The two parts share the same logic and draw from the same cleaned dataset.

---

## Key visual insight

### Alcohol-related hospitalisation gap: Dundee City vs Scotland

This figure shows the difference in European Age-Standardised Rates (Dundee City minus Scotland). Values above zero indicate excess burden in Dundee.

![Dundee vs Scotland gap over time](figures/ARHS_Figure5_diff_over_time.jpg)

Dundee City consistently experiences higher alcohol-related hospitalisation rates
than the Scottish average. The gap persists over time, indicating a sustained
inequality rather than short-term fluctuation.

---

## Aim

The aim of this work was to:

- Clean and standardise a public health dataset
- Explore national and local trends in alcohol-related hospitalisation
- Compare Dundee City with the Scottish average
- Make inequality explicit by measuring differences relative to Scotland
- Present results in a clear, reproducible, and interactive format

The analysis is **descriptive** and does not attempt to infer causality.

---

## Data

The raw dataset, `ARHS_byCouncilArea.csv`, comes from publicly available Scottish health statistics and reports annual alcohol‑related hospital statistics between 1997 and 2024 and is broken down by:

- Council area (local authority)
- Financial year
- Condition (Alcohol‑related condition)
- SMR type

Rates are reported as **European Age‑Standardised Rates (EASR) per 100,000 population**, allowing comparison across areas and over time.

All analysis is based on a single cleaned dataset: `ARHS_byCouncilArea_clean.csv`.

This file is produced in Python and used directly in Power BI.

---

## Tools used

This project combines **Python-based analysis** with a **Power BI dashboard**. Python is used for data cleaning, validation, and analytical logic, while Power BI is used for interactive visualisation and stakeholder-facing reporting.

- **Python** for data cleaning, transformation, and validation
  - **pandas** for filtering, grouping, and aggregation
  - **matplotlib / seaborn** for exploratory plots
  - **Jupyter Notebook** for reproducibility
- **Power BI Desktop** for interactive visualisation
- **DAX** for measures that mirror Python logic
- *(Optional extension)* ArcGIS for spatial visualisation

---

## Analysis process

### 1. Data preparation (Python)

The first notebook prepares a clean, analysis‑ready dataset:

- Loads the raw CSV data and checks data types
- Removes unused quality-flag columns
- Standardises column names and data types
- Converts coded fields into readable labels
- Extracts numeric financial years
- Checks for missing values and duplicate records
- Verifies that no rows were unintentionally dropped

The output is a single cleaned CSV file, `ARHS_byCouncilArea_clean.csv`, used by all downstream analysis and visualisation.

---

### 2. Exploratory data analysis (EDA) (Python)

The second and third notebookes focus on describing patterns in the data:

- Calculates mean EASR values by year, council, and condition
- Compares Dundee City with Scotland using aligned time series
- Explores condition-specific trends
- Calculates simple differences to confirm inequality patterns

Static Python plots were used to validate trends before building interactive visuals.

---

### 3. Visualisation and interaction (Power BI)

- Imported the cleaned CSV without further transformation
- Created DAX measures that replicate Python aggregation logic
- Built focused pages for national trends, comparisons, gaps, and rankings
- Used page-level filters to lock analytical intent
- Applied consistent colour rules to support interpretation

No preprocessing or reshaping is performed in Power BI.

---

### 4. Visual Structure and Logic (Power BI dashboard)

The dashboard is organised into five main views:

1.	**National trend** — Scotland-wide EASR over time
2.	**Dundee vs Scotland** — two-line comparison
3.	**Mental & behavioural disorders** — condition-specific comparison
4.	**Dundee minus Scotland gap** — inequality over time
5.	**Council ranking (latest year)** — cross-sectional comparison

Each page answers a single question and avoids unnecessary visual clutter.

---

## Key insights

- Alcohol‑related hospitalisation rates vary substantially over time and between council areas.
- Dundee City consistently records higher alcohol-related hospitalisation rates than the Scottish average.
- The gap between Dundee City and Scotland is persistent rather than driven by a single year.
- Mental and behavioural disorders due to alcohol account for a large share of the excess burden in Dundee City.
- In the most recent year of data, Dundee City ranks among the councils with the highest excess alcohol-related hospitalisation rates relative to Scotland.

All findings are **descriptive** and intended to highlight patterns rather than explain causes.

---

## Selected visual outputs

The figures below illustrate the main analytical findings. Interactive versions are available in the Power BI dashboard.

### National trend in Scotland

![Alcohol-related hospitalisation rates in Scotland over time](figures/ARHS_Figure1_national_trend.jpg)

*Alcohol-related hospitalisation rates in Scotland show marked changes over time.*

### Dundee City vs Scotland

![Dundee City compared with Scotland over time](figures/ARHS_Figure2_dundee_vs_scotland.jpg)

*Dundee City consistently records higher alcohol-related hospitalisation rates than the Scottish average.*

### Council ranking by latest-year

![Council ranking by excess rate relative to Scotland](figures/ARHS_Figure6_council_ranking.jpg)
*In the most recent year, Dundee City ranks among the councils with the highest excess rates relative to Scotland.*

---

## How to run the project

### Requirements

- Python 3.9+
- pandas
- numpy
- matplotlib
- seaborn
- Jupyter Notebook or JupyterLab

### Running locally

1. Clone the repository
2. Place the raw CSV file in:
   ```
   data/raw/ARHS_byCouncilArea.csv
   ```
3. Run the notebooks in order:
   1. `01_ARHS_byCouncilArea_cleaning.ipynb`
   2. `02_ARHS_byCouncilArea_exploratory_analysis.ipynb`
   3. `03_ARHS_byCouncilArea_inequality_analysis.ipynb`

Figures will be saved to the `figures/` directory.

---

## Limitations

- Analysis is based on aggregated council‑level data
- No individual‑level adjustment beyond age standardisation
- No formal statistical testing or modelling
- Results should be interpreted as comparative, not causal

---

## Future analysis and extensions

Possible extensions include:

- Automate the Python cleaning pipeline
- Link scheduled data updates to Power BI refresh
- Add spatial mapping using council boundaries
- Examining changes before and after major alcohol policy interventions
- Extend condition-specific analysis
- Add brief narrative annotations for non-technical audiences

---

# Licence

This repository is provided for educational and analytical purposes. Please check the original data provider’s licence before reusing the raw data.

---

## Files in the repository

- raw data - data/raw/
  - ARHS_byCouncilArea.csv
- cleaned data - data/raw/
  - ARHS_byCouncilArea_clean.csv
- jupyter notebooks - notebooks/
  - 01_ARHS_byCouncilArea_cleaning.ipynb
  - 02_ARHS_byCouncilArea_exploratory_analysis.ipynb
  - 03_ARHS_byCouncilArea_inequality_analysis.ipynb
- output files  - figures/
   - ARHS_Figure1_national_trend.jpg
   - ARHS_Figure2_dundee_vs_scotland.jpg
   - ARHS_Figure3_mh_conditions.jpg
   - ARHS_Figure4_condition_dumbbell.jpg
   - ARHS_Figure5_diff_over_time.jpg
   - ARHS_Figure6_council_ranking.jpg
   - ARHS_Figure7_mh_ranking.jpg
- power bi files - power_bi/
    - ARHS_byCouncilArea_dashbord.pbix
    - ARHS_dashbord_PowerBI.pdf
    - dax_measures.md
- project overview and links - README.md 

