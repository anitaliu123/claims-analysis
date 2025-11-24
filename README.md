# Assignment 5: Healthcare Claims Data Analysis Assignment 

This project analyzes a sample of **prospective claims data** from Stony Brook University Hospital (May 2024).  
The goal is to understand provider billing patterns, payer mix, diagnoses, procedures, and claim-level charge variations by joining three relational claims files (HEADER, LINE, CODE).

This analysis simulates real responsibilities of:
- Healthcare data analysts  
- Medical billing & compliance analysts  
- Informatics specialists supporting revenue cycle & quality improvement  

## 📁 Repository Structure
   ```
    .venv
    data/
       *.csv 
    notebooks/
        claims_analysis.ipynb
    requirements.txt
    README.md
   ```

## Dataset Description

The dataset consists of **three files** that together form a relational dataset:

### HEADER File `STONYBRK_20240531_HEADER.csv`
One row per **claim**, containing:
- Claim ID  
- Billing/attending/rendering providers  
- Service dates  
- Place of service (POS)  
- Primary payer  
- Work queue information  

### LINE File `STONYBRK_20240531_LINE.csv`
One row per billed **service line**, containing:
- CPT/HCPCS codes  
- Modifiers  
- Charges  
- Units  
- Diagnosis code mappings for the line  

### CODE File `STONYBRK_20240531_CODE.csv`
One row per **diagnosis code**, containing:
- ICD-10 code  
- Diagnosis position on claim  
- Qualifier code  

## How to Run This Project

### Google Colab

1. Open the notebook:  
   `notebooks/claims_analysis.ipynb`

2. On the left sidebar, click the **Files** icon and click **Upload**.

3. Upload all three CSV files:
   - `STONYBRK_20240531_HEADER.csv`
   - `STONYBRK_20240531_LINE.csv`
   - `STONYBRK_20240531_CODE.csv`

4. Run the notebook from top to bottom.

## Key Findings

- The dataset contains 388 unique claims, spanning service dates from September 2023 to May 2024, with an average of 1.34 service lines and 3.96 diagnosis codes per claim.
- SB Internists, SB Surgical Associates, and New York Spine & Brain Surgery were the highest-volume billing providers.
- Medicare accounted for the majority of claim volume (~62%), followed by Healthfirst FFS and Medicaid-managed plans.
- The most frequent diagnoses were acute respiratory failure (J96.01), hyperlipidemia (E78.5), and hypertension (I10), reflecting a high-acuity inpatient population.
- The most frequent procedures were critical care (99291) and inpatient evaluation & management codes (99233, 99223).
- Inpatient (POS 21) and office (POS 11) claims made up over 90% of encounters, with outpatient hospital services showing the highest average total charges per claim.
- Claims with 5 or more service lines were rare and associated with higher charges and more complex encounters.

## Required Libraries 

pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
jupyter

I put these in ``requirements.txt``