# Healthcare Analytics Dashboard (Tableau Public)

An interactive dashboard analysing hospital admissions and billing in a synthetic healthcare dataset.

**Live dashboard:** [View on Tableau Public](https://public.tableau.com/views/HealthcareAnalyticsDashboard_17925612681200/HealthcareAnalyticsDashboard?:language=en-GB&:display_count=n&:origin=viz_share_link)

## Business questions
- How many patients are admitted, and how does volume change month to month?
- How are admissions split between Elective, Emergency and Urgent?
- How does total billing compare across insurance providers?

## Data
- Source: Kaggle, "Healthcare Dataset" by Prasad Patil (synthetic, no real patient data)
- Raw: 55,500 rows, 15 columns
- Period covered: May 2019 to May 2024

## Data cleaning (Python / pandas)
| Step | Rows |
|---|---|
| Raw data | 55,500 |
| Duplicates removed | 534 removed, 54,966 left |
| Zero or negative billing removed | 106 removed, **54,860 final** |

Other changes:
- Fixed patient name casing (for example "LesLie TErRy" became "Leslie Terry")
- Rounded billing amounts to 2 decimals
- Created `Length of Stay` (discharge date minus admission date) and `Age Group`
- Dropped `Doctor` and `Room Number` (not needed for this analysis)

## Dashboard contents
- **KPI:** total admissions (54,860)
- **Monthly trend:** admissions per month
- **Admission type:** Elective, Emergency, Urgent split
- **Billing by insurer:** total billing per provider

The monthly trend excludes May 2019 and May 2024 because the data covers only part of each month, which would show as a misleading drop.

## Key findings
- Admissions are split almost evenly: Elective 18,437, Urgent 18,353, Emergency 18,070
- Monthly admissions stay in a steady range of roughly 800 to 1,000, with one noticeable dip in early 2022
- Billing is similar across all five insurers: Cigna is highest (about 284.3M) and Aetna lowest (about 276.5M), a gap of under 3%

## Limitations
The data is synthetic and generated randomly, so the evenness of the splits reflects how it was made rather than real hospital patterns. This project shows the analysis workflow, not real-world conclusions.

## Tools
Python (pandas) for cleaning, Tableau Public for visualisation.
