## Tutorial 2 — Advanced Data Cleaning (Breakout Assignment)

This document summarises the work completed for the DBP (Diastolic Blood Pressure) breakout task as part of the Emergency Triage Dataset cleaning exercise.

────────────────────────────────────────

DBP (Diastolic Blood Pressure) Cleaning Process

The DBP column was the assigned variable for this group task.

The cleaning process followed these steps:

1. The DBP column was inspected using pandas functions (head, info, describe) to understand its datatype, distribution, and potential missing or unusual values.

2. The column was converted to numeric format using pd.to_numeric with errors='coerce' to handle any non-numeric or invalid entries.

3. Values outside the clinically valid range (30–150 mmHg) were identified as outliers.

4. These invalid values were replaced with NaN to ensure unrealistic measurements did not affect the analysis.

5. Missing values were then imputed using the median of the cleaned DBP column, as the median is more robust to skewed distributions and outliers commonly found in clinical data.

6. A visual inspection (histogram/boxplot) was used to confirm that the cleaned distribution remained clinically reasonable.

────────────────────────────────────────

Clinical Context

DBP (Diastolic Blood Pressure) represents arterial pressure during heart relaxation and is a key vital sign used in assessing cardiovascular function and patient stability.

Accurate cleaning is important because DBP contributes to clinical interpretation and downstream calculations such as Mean Arterial Pressure (MAP).

MAP is calculated using:
MAP = (SBP + 2 × DBP) / 3

This highlights the relationship between DBP and SBP in overall cardiovascular assessment.

────────────────────────────────────────

Other Variables (from Tutorial 2)

The following variables were also addressed during the tutorial:

GCS (Glasgow Coma Scale):
- Converted from string to numeric
- Invalid entries (e.g. "error") replaced with NaN
- Out-of-range values (3–15) handled
- Median imputation applied

Temperature:
- Standardised from mixed formats (Celsius/Fahrenheit/string)
- Converted into consistent Celsius values
- Invalid physiological values removed (32–43°C range)
- Median imputation applied

SBP (Systolic Blood Pressure):
- Converted to numeric
- Out-of-range values handled and imputed

These steps ensured all vital signs were clinically consistent and suitable for analysis.

────────────────────────────────────────

Summary

This exercise demonstrates the importance of combining clinical understanding with data preprocessing techniques. Proper handling of missing values, outliers, and incorrect data types ensures that clinical datasets remain reliable for analysis and interpretation.
