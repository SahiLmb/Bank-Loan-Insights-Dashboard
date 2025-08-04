# Bank Loan Insights Dashboard

## Introduction

**Bank Loan Insights Dashboard** is a Power BI solution for analyzing and visualizing bank loan performance, risk, and trends. The project delivers a full view of lending operations — from executive KPIs to granular record-level data — enabling business leaders, analysts, and stakeholders to make informed decisions with confidence.

This dashboard leverages robust SQL queries (see the included query document) and reproducible DAX measures, with rigorous cross-validation for accuracy. The design emphasizes efficiency, interactivity, and a modern, readable aesthetic.

---

## Features

- **Dynamic KPIs:** Instantly track applications, funding, receipts, interest rates, DTI, and “good vs. bad” loan rates.
- **Drilldown Analytics:** Slice data by state, employee length, purpose, home ownership, grade, and term.
- **Executive Summary & Detailed Views:** Progress seamlessly from high-level metrics to record-level details.
- **Field Parameters:** Easily toggle between multiple fields or breakdowns within a single chart for deeper insights.
- **Optimized Interactivity:** Fine-tuned filters and visual interactions for a user-friendly analytical experience.
- **Modern, Accessible Theme:** Professional dark design with color-coded highlights for intuitive visual cues.

---

## Data & Validation Process

- **SQL Queries:**  
  All key metrics and breakdowns were first queried and validated in SQL, as documented in [`Query-Document-upd.docx`](./Query-Document-upd.docx).
- **Power BI (DAX) Implementation:**  
  SQL logic was then faithfully reproduced using DAX in Power BI, and results **cross-verified** to ensure consistency and accuracy.
- **Efficient Filtering:**  
  Field Parameters in Power BI allow end users to analyze multiple attributes in a single visual.
- **Interactions Editing:**  
  Visual interactions were edited for logical, efficient, and intuitive filtering across all dashboard pages.

---

## Report Structure

The dashboard consists of three main pages, each serving a specific analytical need:

### 1. Analysis (Summary)
- **Purpose:** Quick executive snapshot of overall loan portfolio health.
- **Content:**
  - KPIs: Total applications, funded amount, receipts, average interest rate, average DTI.
  - Good vs. Bad Loans: Visual comparison with detailed breakdowns.
  - Month-over-Month (MoM) and Month-to-Date (MTD) statistics for instant trend analysis.

### 2. Overview
- **Purpose:** In-depth exploration of loan data by key dimensions.
- **Content:**
  - Loan Applications by Month: Identify trends and seasonality.
  - Segmentation by State, Employee Length, Purpose, Home Ownership, Grade, and Term.
  - Good vs. Bad Loans by segment for risk profiling and business insights.

### 3. Details
- **Purpose:** Record-level data analysis and validation.
- **Content:**
  - Tabular view of individual loans: Loan ID, Purpose, Home Ownership, Grade, Sub Grade, Issue Date, Funded Amount, Interest Rate, Installment, Amount Received, Term.
  - Filter, search, and cross-reference capabilities for comprehensive investigation and compliance.

---

## Queries & Measures

All logic behind each KPI and visualization is included in the attached query document. Here are examples of the analytic queries powering the dashboard:

```
-- Total Loan Applications
SELECT COUNT(id) AS Total_Applications FROM bank_loan_data

-- Total Funded Amount
SELECT SUM(loan_amount) AS Total_Funded_Amount FROM bank_loan_data

-- Average Interest Rate
SELECT AVG(int_rate)*100 AS Avg_Int_Rate FROM bank_loan_data

-- Good Loan Funded Amount
SELECT SUM(loan_amount) AS Good_Loan_Funded_amount
FROM bank_loan_data
WHERE loan_status = 'Fully Paid' OR loan_status = 'Current'
```

---
- For MTD/PMTD breakdowns, additional WHERE clauses filter by month.
- See `Query-Document-upd.docx` for the full suite of queries.

---

## How to Use

1. **Open the Dashboard:**  
   Use Power BI Desktop to open or deploy the dashboard file.
2. **Explore & Filter:**  
   Use slicers, filters, and field parameters to view specific segments or change chart breakdowns.
3. **Drill Down:**  
   Click visuals or select filters to view finer details, or move to the Details page for row-level data.
4. **Validate Results:**  
   Cross-check calculations using the query document and your data sources as needed.

---

## Files in This Repository

- **Bank-Loan-Report-Analysis.pdf** — Exported PDF of the Power BI dashboard visuals and summaries.
- **Query-Document-upd.docx** — All SQL queries, filter logic, and KPI definitions for validation and reference.

---

## License

Released under the MIT License.

---

## Feedback & Contributions

Contributions and suggestions are welcome! Please open an issue or pull request with your feedback or improvements.


