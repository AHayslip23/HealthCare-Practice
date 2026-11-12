# HealthCare Practice

A data cleaning, feature engineering and exploratory data analysis project on a hospital admissions dataset (55,500 patient records). The dataset includes age, gender, blood type, medical condition, admission type, insurance provider and billing amount.

## Repository Contents

| File | Description |
|---|---|
| `Healthcare Data Analysis.ipynb` | Main notebook: cleaning, feature engineering and EDA |
| `healthcare_dataset.csv` | Raw dataset (55,500 rows) |
| `Medical Condition.png` | Exported chart of admissions by medical condition |

## Commit History

### `6df1b45`: Initial commit (2026-08-02)
- Created the repository with a `.gitattributes` file.

### `90f54d8`: Commit #1, data cleaning, feature engineering and EDA (2026-08-02)
- **Added the files:** `healthcare_dataset.csv`, the notebook, and `Medical Condition.png`.
- **Cleaning:**
  - dropped `Room Number`
  - converted the admission and discharge dates to datetime
  - rounded `Billing Amount` to 2 decimals
- **Feature engineering:**
  - one-hot encoded Gender, Blood Type, Admission Type and Test Results
  - added an age range column
  - added admission and discharge year and month-year columns
  - added `Is_Lifestyle_Condition` (diabetes, hypertension, obesity) and `Is_Chronic_Condition` (asthma, cancer, arthritis) flags
- **Data quality checks:**
  - checked for nulls and duplicates (534 duplicate rows)
  - removed rows with duplicate patient names, then dropped the `Name` column
  - checked `Age` and `Billing Amount` for outliers with the IQR method (none found)
- **EDA:**
  - histograms of age and billing amount
  - yearly admissions by condition, with lifestyle vs. chronic conditions side by side
  - admission type by year
  - pivot tables of condition by admission type, blood type by condition, gender by blood type, and condition by insurance provider
  - admissions by age category

### `7adfd4d`: Commit #2, EDA nearly finished (2026-10-16)
- **Rebuilt the age brackets with `pd.cut`:** 0–17, 18–34, 35–49, 50–64, 65–74, 75–89 and 90+.
- **Removed rows with negative billing amounts.**
- **Reworked the EDA into consistent year-by-year breakdowns:**
  - patient composition by gender
  - admissions per year by medical condition, blood type, admission type, age range and insurance provider
  - billing amount by insurance provider, age bracket, gender and medical condition
- **Added a notebook checkpoint file.**

## Tools
Python, pandas, NumPy, matplotlib, seaborn, Jupyter Notebook
