# Healthcare-Patient-Analytics-Dashboard--Excel
# Healthcare Admissions Analysis

Excel project analysing ~55K hospital admissions (May 2019 – May 2024), cleaned with Power Query, with a summary sheet and an interactive dashboard.

## Data
`healthcare_dataset`: 15 source columns (patient demographics, condition, admission/discharge dates, insurer, billing, medication, test results). The data appears synthetic, so group differences are very small.

## Cleaning (Power Query)
- Capitalised the Name column
- Removed exact duplicate rows (all columns), leaving 54,966 rows
- Flagged 108 negative Billing Amounts in `Billing Validation` rather than deleting them

## Added columns
| Column | Purpose |
|---|---|
| Billing Clean | Billing Amount, blank where invalid |
| Length of Stay | Discharge Date – Date of Admission (days) |
| Age Group | 13-29, 30-44, 45-59, 60-74, 75+ |
| Admission Month | First day of the admission month |
| In Dashboard Filter | 1 if the row matches the dashboard dropdowns |

## Sheets
- **Summary** – key metrics, breakdowns by condition, admission type, insurer and age group, monthly trend, 2 charts
- **Dashboard** – six dropdown filters (condition, admission type, insurer, age group, gender, year) driving KPI cards and six charts
- **Dashboard Data** – filter lists and chart source tables (formula-driven)

## Findings
- Average billing is ~$25.6K and varies little across conditions, insurers or age groups
- Length of stay and billing are unrelated (correlation ≈ 0)
- Monthly admissions are flat at roughly 900–1,000

## Notes
- Billing metrics exclude the invalid-billing rows
- First and last months are partial
- Everything is formula-driven and updates when the query is refreshed.

  ## Data Source
  https://www.kaggle.com/code/basantabdelmwla/healthcare/input?select=healthcare_dataset.csv
