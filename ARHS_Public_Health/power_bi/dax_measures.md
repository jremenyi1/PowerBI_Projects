# DAX Measures – Technical Notes

- These notes describe the **Power BI measures used in the ARHS dashboard** and explain the logic behind them in plain terms.

- Power BI is used **for visualisation only**. All measures are designed to **match the calculations already performed in Python**.

- No data cleaning, reshaping, or aggregation happens inside Power BI.

---

## Data used by Power BI

Power BI connects directly to the cleaned dataset produced by the Python pipeline:
- `data/processed/ARHS_byCouncilArea_clean.csv`

This file already contains:

- Council area
- Financial year
- Condition category
- Measure type
- European age-standardised rate (EASR)

Power BI does not modify these fields.

---

## Core measures

### EASR_Rate

This is the base measure used across the dashboard.

What it does:

- Calculates the **mean European age-standardised rate**
- Respects filters for council, year, condition, and measure type

Why it exists:

- Keeps the logic simple and transparent
- Matches the Python groupby + mean calculation exactly

---

### Scotland_EASR_Rate

This measure calculates the **national average for Scotland**.

What it does:

- Ignores council-level filters
- Responds to year, condition, and measure type filters

Why it exists:

- Provides a consistent baseline for comparison
- Avoids hard-coding national values

---

### EASR_Diff_vs_Scotland

This is the main inequality measure.

What it does:

- Subtracts the Scotland rate from the council rate

`(Council EASR − Scotland EASR)`

How to read it:

- Positive value → higher rate than Scotland
- Zero → same as Scotland
- Negative value → lower rate than Scotland

Why it exists:

- Makes inequality visible without relying on side-by-side charts
- Matches the inequality calculations used in Python

---

## Latest-year measures

### LatestYear_EASR_Rate

This measure returns the **EASR for the most recent year** in the dataset.

What it does:

- Automatically detects the latest financial year
- Avoids hard-coding a specific year

Why it exists:

- Keeps rankings up to date when new data is added

---

### LatestYear_EASR_Diff_vs_Scotland

This measure calculates the **latest-year inequality**.

What it does:

- Applies the difference-vs-Scotland logic
- Restricts the result to the most recent year

Why it exists:

- Supports council ranking visuals
- Highlights current excess burden

---

### Design principles

All Power BI measures follow the same rules:

- No duplication of Python logic
- No hidden transformations
- Fully filter-responsive
- Easy to audit and explain

If a value appears in Power BI, it should be possible to reproduce it in Python.

---

### Relationship to Python analysis

- Python handles data cleaning, validation, and analytical logic
- Power BI handles visual exploration and presentation
- DAX measures replicate Python calculations, not replace them

This separation keeps the project **reproducible, consistent, and easy to maintain**.


