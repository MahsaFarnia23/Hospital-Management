# Hospital Management SQL Analytics (SQLite)

A complete end-to-end SQL analytics project using a hospital management dataset.  
This project demonstrates practical data analyst skills in **data modeling assumptions**, **KPI design**, **operational analytics**, **revenue intelligence**, **patient segmentation (SQL-only)**, and **time-based trend analysis**.

---

## 📑 Table of Contents
- [📘 Project Overview](#-project-overview)
- [🎯 Project Objectives](#-project-objectives)
- [💼 Business Problem](#-business-problem)
- [🧩 Key Deliverables](#-key-deliverables)
- [📌 Key Results Snapshot](#-key-results-snapshot)
- [✅ Executive Summary](#-executive-summary)
- [🧠 Management Recommendations](#-management-recommendations)
- [▶️ How to Run](#️-how-to-run)


---

## 📘 Project Overview
This SQL project performs a complete analysis of a hospital management dataset using **SQLite**.  
It evaluates:
- Doctor and appointment **operational efficiency**
- **Revenue drivers** and financial concentration risk
- **Patient behavior** and segmentation (Frequency / Monetary / Recency)
- **Temporal patterns** (monthly trends, seasonality, and growth/decline)

---

## 🎯 Project Objectives
Hospital management wants to better understand:
- Operational **efficiency** of doctors and appointments
- **Revenue** drivers and cost/value distribution
- **Patient behavior** patterns and segmentation (SQL-only)
- Workload imbalance, seasonality, and growth/decline **trends**

---

## 💼 Business Problem
Hospital management requires a data-driven understanding of daily operations and financial performance to support:
- staffing and scheduling decisions,
- service mix and investment prioritization,
- workflow monitoring (appointment → treatment → billing),
- proactive planning based on seasonality and demand changes.

---

## 🧩 Key Deliverables
To make the analysis reusable in a production setting, the project includes working views such as:
- `vw_doctor_monthly_performance` — monthly doctor appointments + revenue KPIs  
- `vw_specialization_revenue` — total revenue + revenue share by specialization  
- `vw_patient_value_segments` — patient segmentation (Frequency/Monetary/Recency)  
- `vw_appointment_to_billing_funnel` — Appointment → Treatment → Billing funnel KPIs  
[sql](docs/data_dictionary.md)


---

## 📌 Key Results Snapshot (High-signal KPIs)
### Funnel Performance (Appointment → Treatment → Billing)
- Appointment → Treatment conversion: **50%** (200 treated out of 400 appointments)

| Appointments | Treated Appointments | Appointment → Treatment Rate | Appointment Drop-off |
|---:|---:|---:|---:|
| 400 | 200 | 0.50 (50%) | 0.50 (50%) |


- Treatment → Billing conversion: **100%** (no downstream revenue leakage once treatment occurs)

| Patients with Treatment | Treated Patients with Billing | Treatment → Billing Rate | Treatment → Billing Drop-off |
|---:|---:|---:|---:|
| 48 | 48 | 1.00 (100%) | 0.00 (0%) |


### Revenue Drivers
- Revenue share by specialization: Pediatrics **46.91%**, Dermatology **35.13%**, Oncology **17.95%**
  
| Specialization | Total Revenue | Revenue Share |
|---|---:|---:|
| Pediatrics | 1,289,294.61 | 0.4691 (46.91%) |
| Dermatology | 965,566.84 | 0.3513 (35.13%) |
| Oncology | 493,428.71 | 0.1795 (17.95%) |

- Top treatment types by revenue: **Chemotherapy** ranks #1, followed by imaging/diagnostics (X-Ray, MRI, ECG) 

| Treatment Type | Total Revenue |
|---|---:|
| Chemotherapy | 662,548.04 |
| X-Ray | 548,881.25 |
| MRI | 535,296.48 |
| ECG | 509,745.97 |
| Physiotherapy | 491,818.42 |


### Risk Exposure
- Revenue concentration: **Top 5 doctors generate ~60% of total revenue**

| Doctor ID | First Name | Last Name | Total Revenue | Revenue Share |
|---|---|---|---:|---:|
| D005 | Sarah | Taylor | 394,356.89 | 0.1435 (14.35%) |
| D006 | Alex | Davis | 339,280.84 | 0.1235 (12.35%) |
| D001 | David | Taylor | 336,851.92 | 0.1226 (12.26%) |
| D010 | Linda | Wilson | 304,846.08 | 0.1109 (11.09%) |
| D003 | Jane | Smith | 279,957.14 | 0.1019 (10.19%) |

- Highest volatility (provider-level): doctors such as **D008** and **D005** show the widest monthly revenue ranges

| Doctor ID | First Name | Last Name | Avg. Monthly Revenue | Revenue Range |
|---|---|---|---:|---:|
| D008 | Linda | Brown | 21,305.28 | 75,074.93 |
| D005 | Sarah | Taylor | 32,863.07 | 74,900.79 |
| D010 | Linda | Wilson | 27,713.28 | 58,190.75 |
| D003 | Jane | Smith | 27,995.71 | 56,701.70 |
| D006 | Alex | Davis | 37,697.87 | 52,088.64 |


### Patient Behavior (SQL-only Segmentation)

| Patient Segment | Patient Count |
|---|---:|
| Chronic high-frequency patients | 20 |
| Frequent low-cost patients | 16 |
| Other patients | 12 |


### Temporal Patterns
- Demand peak: 

| Month | Appointment Count |
|---|---:|
| 2023-04 | 50 |
| 2023-01 | 40 |

- Lowest demand: **September (22 appointments)**  
- Revenue peak: 

| Month | Monthly Revenue |
|---|---:|
| 2023-04 | 592,871.50 |
| 2023-05 | 569,006.50 |
| 2023-06 | 560,830.22 |

 weakest revenue: **August (~291K)**
- MoM analysis shows cyclical growth/decline and occasional divergence between volume vs value.

---

## ✅ Executive Summary
This project analyzes hospital operational and financial data to identify performance gaps, revenue drivers, and strategic risks.  
Results show that **doctor workload and patient demand are unevenly distributed over time**, creating periods of underutilization and overload.  
From a financial perspective, **Pediatrics and Dermatology generate the majority of revenue**, while **Oncology delivers the highest revenue per appointment**, indicating high-value but lower-volume activity.  
Revenue and appointment trends exhibit **clear seasonality**, with strong performance in spring and early summer and notable slowdowns in late summer.  
Patient segmentation reveals a **small group of chronic, high-frequency patients contributing disproportionately to total revenue**, increasing operational dependency risk.  
Overall, the analysis highlights the need for **flexible staffing, revenue diversification, and proactive management of high-impact patient and provider segments** to improve efficiency and financial resilience.

---

## 🧠 Management Recommendations
- **Adopt flexible staffing models** aligned with seasonal demand patterns, increasing doctor availability during spring and early summer peak periods while optimizing resources during late-summer slowdowns.

- **Rebalance doctor workloads within specializations**, particularly in Pediatrics and Dermatology, where workload variance indicates opportunities to reduce burnout and improve appointment availability through more even distribution.

- **Prioritize investment in high-value specializations**, especially Oncology, which generates the highest revenue per appointment, while maintaining sufficient capacity in high-volume specialties to ensure revenue stability.

- **Mitigate revenue concentration risk** by reducing dependency on a small number of top-performing doctors through cross-training, patient redistribution, and broader provider utilization.

- **Proactively manage high-frequency, high-cost patient segments** by introducing care coordination or follow-up optimization strategies to reduce operational strain while preserving revenue contribution.


---

## ▶️ How to Run
1) Load CSV files into SQLite and create the database schema.  
2) Run `sql/00_create_views.sql` to generate working views.  
3) Run analysis queries from the `sql/` folder or read details in `docs/`.

---

