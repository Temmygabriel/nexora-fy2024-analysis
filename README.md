# Nexora Software FY2024 Financial Analysis

Raw transaction data from a fictional B2B SaaS company. 522 rows. Six date formats. Department names spelled five different ways. Two duplicate transactions. One month of cloud costs entered in GBP inside a USD column.

This project cleans all of it and finds four things the CFO needed to know before FY2025 planning.

---

## What's in this repo

- `data/nexora_raw_data.xlsx` — the original messy file with a Cleaning Log sheet documenting every issue found
- `data/nexora_cleaned.xlsx` — cleaned dataset with every fix applied and documented in new columns
- `dashboard/nexora_dashboard.pbix` — Power BI dashboard with KPI cards, quarterly charts, and insight annotations
- `screenshots/` — visuals for quick reference

---

## The four findings

Marketing spent $278K more in H1 than H2. Q4, their lowest marketing spend quarter, delivered $4.1M in revenue, the highest of the year. That number needs explaining before anyone approves the FY2025 marketing budget.

Cloud Infrastructure costs went up every single month of FY2024. Each individual increase looked small. Cumulative effect across the year was significant overspend by December. The annual total hides the trend; the monthly breakdown exposes it.

Professional Services outperformed expectations every month without exception. At $1.57M actual, it was the most consistent revenue line in the business, but got no attention because leadership tracked subscriptions. That's a gap worth fixing.

Q4 was the strongest quarter by a distance at $2.39M net. But the full year net income still missed the budget target. The recovery was real; it just came too late.

---

## Tools used

Google Sheets for data cleaning, Excel for analysis and SUMIFS formulas, Power BI for the dashboard.

---

## Data cleaning approach

Every cleaning decision is documented in the Cleaning Log sheet inside `nexora_raw_data.xlsx`. The methodology: never overwrite source data, always add new columns, always flag anomalies rather than silently dropping them.

Key fixes applied:
- 2 duplicate Transaction IDs removed
- 6 date formats standardised to YYYY-MM-DD using REGEXMATCH + DATEVALUE
- 19 department name variants mapped to 6 canonical names via VLOOKUP lookup table
- 5 GBP rows converted to USD at 1.27
- 2 negative revenue entries reclassified as Contra-Revenue
- Missing amounts flagged for stakeholder review

---

Analyst: Temmygabriel | github.com/Temmygabriel
