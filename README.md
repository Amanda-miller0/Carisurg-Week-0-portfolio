# Carisurg-Week-0
This repository is for the submission Week 0's assignments

# 🏥 CariSurg MedTech Pathways — Week 0 Tutorial 1

## Python for Basic Data Exploration & Cleaning  
Mercer General Hospital | Clinical AI & Innovation Unit

---

## Overview
This project is part of the Week 0 training tutorial for the Clinical AI & Innovation Unit. The goal was to learn basic Python and perform initial data cleaning on a hospital triage dataset.

---

## Objective
To clean the **Gender column** in a real-world clinical dataset by:
- Identifying inconsistent values
- Standardizing them into a binary format
  - 1 = Male  
  - 0 = Female

---

## Steps Completed

### 1. Data Loading
- Imported dataset using `pandas`
- Inspected shape and column types

### 2. Data Exploration
- Checked unique values in the `Gender` column
- Used `.unique()` and `.value_counts()` to identify inconsistencies

### 3. Data Cleaning
- Created a mapping dictionary to standardize values:
  - Male, MALE, 1 → 1  
  - Female, FEMALE, 0 → 0
- Applied `.map()` to create a cleaned column

### 4. Verification
- Confirmed no missing values after cleaning
- Replaced original column with cleaned version

---

## Tools Used
- Python
- Pandas
- NumPy
- Google Colab

---

## Outcome
A cleaned dataset with a standardized Gender column ready for further analysis in future tutorials.

---

## File Included
- `Week0_Tutorial1_GenderCleaning.ipynb`



---
