# Carisurg-Week-0
This repository is for the submission Week 0's assignments

# 🏥 CariSurg MedTech Pathways — Week 0 Project

Mercer General Hospital | Clinical AI & Innovation Unit

---

## Overview
This repository contains Week 0 work for the CariSurg MedTech Pathways programme.  
The project focuses on exploring, cleaning, and visualising a real-world emergency triage dataset using Python.

The goal is to build foundational skills in:
- Clinical data understanding
- Data cleaning and preprocessing
- Handling missing values and outliers
- Basic data visualisation
- Connecting clinical meaning to data science

---

## 📌 Tutorial 1 — Gender Data Cleaning

### Objective
Standardise the Gender column into a binary format:
- 1 = Male  
- 0 = Female  

### Steps Completed
- Loaded dataset using pandas
- Identified inconsistent gender values (e.g. "MALE", "female", "1", "0")
- Applied mapping dictionary to standardise values
- Verified cleaning using `.head()` and `.value_counts()`

### Outcome
A cleaned Gender column suitable for analysis in downstream tasks.

---

## 📌 Tutorial 2 — Clinical Data Cleaning (Vital Signs)

### Objective
Clean and standardise multiple clinical variables to ensure consistency and clinical validity.

---

### 🧠 Variables Cleaned

#### GCS (Glasgow Coma Scale)
- Converted to numeric
- Handled invalid entries (e.g. "error")
- Removed out-of-range values (3–15)
- Imputed missing values using median

#### SBP (Systolic Blood Pressure)
- Converted to numeric
- Removed physiologically impossible values (<50 or >250)
- Imputed using median

#### DBP (Diastolic Blood Pressure)
- Removed values outside 30–150 mmHg
- Imputed using median
- Used in MAP calculation

#### Temperature
- Standardised mixed formats (°C, °F, strings)
- Converted all values to Celsius
- Removed invalid physiological values (32–43°C)
- Imputed using median

#### Pulse, RR, FiO2
- Converted to numeric
- Removed out-of-range values based on clinical thresholds
- Imputed missing values using median (FiO2 preserved clinically valid 21–100%)

#### MAP (Mean Arterial Pressure)
- Recalculated using:
  - MAP = (SBP + 2 × DBP) / 3
- Used SBP and DBP to ensure clinical consistency

---

## 📊 Visualisations Created

The following plots were generated for exploratory data analysis:

- Gender distribution (bar plot)
- GCS distribution (histogram)
- Pulse distribution (histogram with clinical thresholds)
- SBP vs DBP (scatter plot with trend reference)
- Age vs Pulse (scatter plot with clinical ranges)
- Vital signs overview (boxplots for all variables)

These visualisations help:
- Identify distributions
- Detect outliers
- Understand relationships between variables
- Validate clinical plausibility

---

## 🏥 Clinical Context

This dataset represents emergency department triage data.

Key clinical insights:
- GCS assesses consciousness (3 = severe impairment, 15 = normal)
- SBP/DBP indicate blood pressure and cardiovascular status
- MAP reflects organ perfusion
- Pulse and RR indicate physiological stress
- Temperature indicates infection or systemic issues
- FiO2 indicates oxygen therapy level

---

## ⚠️ Key Data Cleaning Principles Used

- Convert all numeric fields using `pd.to_numeric(errors='coerce')`
- Replace physiologically impossible values with NaN
- Use median imputation for robustness
- Standardise inconsistent formats (especially temperature)
- Validate using clinical reference ranges, not just statistics

---

## 📁 Files Included

- Week0_Tutorial1_GenderCleaning.ipynb
- Week0_Tutorial2_ClinicalCleaning.ipynb
- Generated plots (.png files)

---

## 📌 Summary

This project demonstrates how clinical understanding and data science techniques combine to produce clean, reliable healthcare datasets suitable for analysis and modelling.

Proper preprocessing ensures that downstream insights are clinically valid and not distorted by errors, outliers, or inconsistent data entry.
