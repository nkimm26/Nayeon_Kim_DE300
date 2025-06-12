## CarLiOn Project Readme

### Overview

This Jupyter notebook performs a two-part analysis on a global tourism‐economy dataset:

1. **Missing Data Exploration & Imputation**

   * Visualizes patterns of missingness
   * Uses `missingno` for diagnostics
   * Applies Random-Forest MICE (via `miceforest`) to impute missing entries

2. **Relational & Correlation Analysis**

   * Loads the cleaned data into an in-memory DuckDB instance
   * Runs SQL queries to compute economic and governance indicators by continent
   * Calculates and visualizes Pearson correlations between tourism exports and six Worldwide Governance Indicators

---

### Files

* DE300_project_CarLiOn.ipynb
* wgidataset.xlsx
* world_tourism_economy_data.csv

---

### Outputs & Visuals

* **Missingness plots** (using `missingno`)
* **Imputed dataset** stored as a Pandas DataFrame
* **DuckDB-driven summary tables** for:

  * GDP per capita
  * Tourism export figures
  * Governance indicators (e.g., Regulatory Quality)
* **Correlation heatmap** of tourism exports vs. governance metrics

---

### Notebook Structure

1. **Setup & Imports**
2. **Data Ingestion**
3. **Missing Data Exploration**
4. **Imputation with `miceforest`**
5. **Relational Analysis (DuckDB)**

   * Country-to-continent mapping
   * Aggregations by continent
6. **Correlation Analysis**

   * Pairwise Pearson correlations
   * Visualization with Seaborn/Matplotlib

