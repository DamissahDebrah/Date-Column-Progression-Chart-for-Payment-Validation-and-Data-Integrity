# 📊 Data Column Progression Chart – Power BI Project

## Project Overview

This Power BI dashboard was developed to track and validate the completeness of key date-related fields in the training records of PQP Marketing Consult. The aim was to ensure data accuracy in critical columns such as training start dates and payment installment dates.

---

## 🔍 Problem Statement

The institution's dataset contained inconsistent or missing values in important date columns:
- Start Date
- Payment Category 1 Date
- Payment Category 2 Date
- Payment Category 3 Date

These gaps made it difficult to monitor participant onboarding, payment status, and revenue projections. The data team needed a simple yet powerful way to visualize and correct these issues.

---

## ✅ Solution & Actions Taken

- **Data Cleaning & Validation:**
  - Assessed each column for missing or incorrect values.
  - Created a custom **DAX measure** to dynamically flag records as **Corrected**, **Not Corrected**, or **N/A**.
  - Used this logic to filter data, color visuals, and build progress indicators.

- **Dashboard Features:**
  - Progress bars to visually represent the percentage of corrected vs. uncorrected data.
  - Color-coded bars (✅ Green for corrected, ❌ Red for not corrected).
  - KPI cards for revenue, total registration, activation, and conversion ratio.

- **Correction Progress:**
  - `Start Date`: 76.3% Corrected | 23.7% Not Corrected
  - `Payment Category 1`: 99.9% Corrected
  - `Payment Category 2`: 89.16% Corrected
  - `Payment Category 3`: 99.07% Corrected

---


## 📈 Outcome & Impact

- Helped the organization track and improve data quality across multiple fields.
- Enabled data teams to focus correction efforts on the most critical gaps.
- Strengthened data-driven reporting and ensured cleaner input for revenue dashboards.
- Supported operational decision-making with more reliable backend data.

---

## 🎯 What I Learned

- How to audit and visualize **data integrity** using Power BI.
- Designing progress-tracking dashboards for internal use.
- Translating backend data cleaning into actionable visuals for stakeholders.
- Emphasized the importance of **data quality in decision-making pipelines**.

---

## 🛠️ Tools Used

- Power BI
- Power Query (Data Cleaning)
- DAX for KPIs and metrics

---

![ Data Column Progression Chart - Full View]((https://github.com/DamissahDebrah/Date-Column-Progression-Chart-for-Payment-Validation-and-Data-Integrity/blob/main/Date%20Column%20Validity.png)

---
## 🔢 DAX Logic Used

The following DAX measure was used to identify the status of each row for validation:

```dax
Start_Date_Identifier = 
IF(
    AND(
        'Global'[1st Installment] > 0, 
        ISBLANK('Global'[Start Date])
    ), 
    "Not corrected",
    IF(
        ('Global'[1st Installment] > 0 && NOT ISBLANK('Global'[Start Date])), 
        "Corrected",
        IF(
            AND(
                'Global'[2nd Installment] > 0, 
                NOT ISBLANK('Global'[Payment Date 2nd])
            ), 
            "Corrected",
            "N/A"
        )
    )
)

---

**Damissah Deborah E.**  
📧 Email: [damissahdeborah@gmail.com](mailto:damissahdeborah@gmail.com)
