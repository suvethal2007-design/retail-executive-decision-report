# retail-executive-decision-report
A Business Intelligence capstone project on retail order data (Commerce domain). It turns 12 raw, messy order records into a decision-ready analysis for the Sales Manager and the C-suite.
# Retail Orders: Executive Decision Report

A Business Intelligence capstone project on retail order data (Commerce domain). It turns 12 raw, messy order records into a decision-ready analysis for the Sales Manager and the C-suite.

## Business question
Where does revenue come from, where is it leaking, and what should we do in the next 90 days?

## Deliverables
| File | Description |
|---|---|
| `Executive_Decision_Report.pdf` | 14-slide executive deck: summary, methodology, key revenue drivers, risk areas, 3 strategic recommendations, ROI projections, implementation timeline |
| `Retail_Executive_Analysis.ipynb` | Final analytical notebook: data cleaning, KPIs, drivers, risks, ROI scenarios |
| `Retail_KPI_Workbook.xlsx` | Source workbook (raw orders and KPI dictionary) |
| `charts/` | Charts used in the deck |

## Approach
1. **Audit:** checked the raw data against the data dictionary rules.
2. **Clean:** removed 1 duplicate order, normalised text (case), repaired "two" to 2, and quarantined 4 orders that broke validation rules (invalid or missing date, missing city, negative quantity, 105% discount).
3. **Measure:** computed the 8 KPIs defined in the KPI dictionary (revenue, orders, AOV, quantity, average discount, paid and pending orders, payment success rate).
4. **Diagnose:** analysed revenue by category, segment and city, and payment health.
5. **Recommend:** three actions with ROI scenarios (conservative, base, upside).

## Key findings
- **Booked revenue is ₹13,059 from 7 clean orders, but only ₹6,013 (46%) is collected.**
- Payment success rate is **57%**.
- **Course Access** is 65% of revenue, but it accounts for all Pending and Refunded value.
- **Learning Kit** is 35% of revenue and 100% collected.
- **Bengaluru** is the largest city by revenue, but only 33% of its revenue is collected.
- Only **7 of 12** raw rows were usable. All 3 Mentor Session orders were rejected, so that category is invisible in the KPIs.

## Recommendations
1. **Close the payment gap:** reminders, payment retries and a daily Pending queue.
2. **Gate data at capture:** validation rules in the order form and a weekly data-quality report.
3. **Bundle Learning Kit with Course Access:** use the reliably collected product as an add-on, with a discount cap.

Base-case projection: about ₹96k annual gain on ₹35k assumed investment (about 4-month payback).

## Assumptions and limitations
- The clean sample is small (7 orders over 16 days), so results are directional, not a forecast.
- The missing discount on RT-1003 was set to 0%. Using 15% instead changes revenue by only ₹225.
- ROI costs and recovery rates are planning assumptions. They can be edited in the `PARAMS` and `COST` cells of the notebook.

## How to run
Keep `Retail_KPI_Workbook.xlsx` in the same folder as the notebook.

```bash
pip install pandas matplotlib openpyxl jupyter
jupyter notebook Retail_Executive_Analysis.ipynb
```

## Tools
Python (pandas, matplotlib), Jupyter, openpyxl.
