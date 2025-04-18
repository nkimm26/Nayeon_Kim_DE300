# DATA_ENG 300 Homework 1 readme

### Overview

The dataset is extracted from `T_F41SCHEDULE_B43.zip'. The goal is to identify and handle missing values in key columns, apply data cleaning techniques, and answer analytical questions.

---

### Contents

- `Kim_HW1_DE300.ipynb`: The main Jupyter Notebook containing all analysis, code, and commentary.
- `T_F41SCHEDULE_B43.zip`: The dataset used (not included in this repo for privacy reasons).

---

### Setup
1. Install required Python packages:
    pip install pandas numpy re matplotlib seaborn 
2. Ensure the data file `T_F41SCHEDULE_B43.zip` is located in the same directory as the notebook and extract the data.

---

### Key Questions Addressed

#### Question 1: Investigate Missing Data
- Task:
  - Impute missing values into the dataset
- A cleaned version of the dataset 'inventory_cleaned' is created using `inventorycopy()`.
- Columns analyzed: `CARRIER`, `CARRIER_NAME`, `MANUFACTURE_YEAR`, `NUMBER_OF_SEATS`, `CAPACITY_IN_POUNDS`, and `AIRLINE_ID`.
- Output:
  - Updated dataset with filled in missing values

#### Question 2: Data Cleaning
- Task:
    - Standardize and transform the data
- Columns analyzed: 'MANUFACTURER', 'MODEL', 'AIRCRAFT_STATUS', and 'OPERATING_STATUS'
- Output
  - Count of unique entries for each column analyzed
  - Updated dataset with standardized entries

#### Question 3: Remove Missing Data
- Task:
  - Remove data rows that still have missing values
- Output:
  - Updated dataset with 132313 rows

#### Question 4: Transformation and Derivative Variables
- Task:
  - Check skewness for the columns 'NUMBER_OF_SEATS' and 'CAPACITY_IN_POUNDS'
  - Implement Box-Cox transformation to make variables more "normal-like"
- Outputs:
  - Amount of skewness before and after transformation for specified columns
  - Histogram of the before and after transformation for specified columns (total of 4 histograms)

#### Question 5: Feature Engineering
- Task:
  - Create 'SIZE' column by the quartiles of 'NUMBER_OF_SEATS'
  - Analyze proportion of operating aircrafts and status of aircraft grouped by the size group
- Outputs:
  - Barplot and table of the proportion of operating status by size
  - Barplot and table of the proportion of aircraft status by size

---

Tools Used

- Python 3
- pandas – Data manipulation and analysis
- matplotlib / seaborn – Visualization (if used)
- re - Regular expression
- boxcox - Box-Cox transformation
- Jupyter Notebook – Interactive analysis environment


