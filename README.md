MoPhones Credit Portfolio Health & Customer Experience Review 
1) Objective
This project assesses the performance of MoPhones’ credit portfolio and examines how repayment risk aligns with customer sentiment (NPS). The aim is to deliver leadership‑ready insights and actionable recommendations to strengthen credit policy and operational execution.

2) Business Context
MoPhones offers smartphones through installment credit, which increases accessibility but introduces several risks:

Default risk: balances unlikely to be recovered

Delinquency risk: accounts progressing into arrears

Customer experience risk: collections activity potentially harming satisfaction and loyalty

Long‑term success requires balancing portfolio health, repayment outcomes, and customer trust.

3) Dataset Overview
Credit Portfolio Snapshots (CSV)

Credit Data - 01-01-2025.csv

Credit Data - 30-03-2025.csv

Credit Data - 30-06-2025.csv

Credit Data - 30-09-2025.csv

Credit Data - 30-12-2025.csv
These files capture account‑level conditions throughout 2025 (DPD, balances, statuses, payments, etc.).

Customer Experience Data (XLSX)

NPS Data (1).xlsx
Contains survey responses tied to loan IDs and 0–10 NPS scores.

4) Methodology
Data Cleaning & Standardization

Resolved schema inconsistencies (e.g., blank headers)

Addressed missing values

Standardized numeric and date parsing

Feature Engineering

Created age bands (18–25, 26–35, 36–45, 46–55, 55+)

Built affordability‑style segments using a proxy where income data was missing

Portfolio Analysis  
Focused on five key metrics:

PAR 30+

Default rate

Repayment rate

Average DPD

Active vs closed ratio
Performed trend analysis across all snapshots and identified high‑risk segments.

Credit × NPS Linkage

Merged the latest credit snapshot with NPS data

Compared sentiment across current, arrears, and default groups

Data Quality Assessment

Flagged missing fields, inconsistencies, and structural gaps

Outlined a future‑state analytical data model

5) Deliverables
Notebook: deliverables/MoPhones_Credit_Case_Study.ipynb

Slide deck (12 slides): deliverables/MoPhones_Credit_Case_Study_Slides.md

Analysis script: scripts/mophones_case_analysis.py

Generated outputs:

analysis_summary.json

portfolio_metrics.csv

age_segment_metrics.csv

6) Key Insights
Portfolio risk rose significantly through 2025 (higher PAR30, defaults, and DPD).

Repayment rates stayed mostly flat, indicating collections did not counteract worsening risk.

NPS scores were substantially lower for customers in arrears or default.

A high‑risk age group emerged, though demographic anomalies suggest caution before embedding policy changes.

7) Recommendations
Adopt risk‑tiered collections strategies aligned to DPD stages.

Implement pre‑delinquency and early‑arrears interventions to reduce roll rates.

Monitor customer impact alongside recovery metrics (e.g., cure rate + NPS change).

Prioritize data model enhancements (transaction‑level payments, standardized statuses, behavioral event tracking).

8) Assumptions
Snapshot files represent point‑in‑time portfolio states.

ACCOUNT_STATUS_L2 is treated as the primary operational status.

total_income and duration were not available, preventing direct income‑based calculations.

Affordability proxy (weekly_rate × 4.33) is used only for directional segmentation.

9) Data Limitations
Schema drift across snapshots (e.g., unnamed columns).

High missingness in some payment fields.

Implausible demographic patterns (age clustering) requiring source verification.

Lack of transaction‑level payment data limits behavioral and causal analysis.

10) How to Run the Project
Code
# From repository root
python scripts/mophones_case_analysis.py
This generates all reproducible outputs in deliverables/outputs/.
Then open the notebook:
deliverables/MoPhones_Credit_Case_Study.ipynb

11) Tools Used
Python 3 (standard library only)

csv, json, datetime, statistics, xml.etree.ElementTree, zipfile, pathlib

Jupyter Notebook (.ipynb)

Markdown‑based slide deck
