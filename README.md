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

| Appointments | Treated | Conversion | Drop-off |
|---:|---:|---:|---:|
| 400 | 200 | 0.50 (50%) | 0.50 (50%) |

- Treatment → Billing conversion: **100%** (no downstream revenue leakage once treatment occurs)

| Patients with Treatment | Treated Patients with Billing | Treatment → Billing Rate | Treatment → Billing Drop-off |
|---:|---:|---:|---:|
| 48 | 48 | 1.00 (100%) | 0.00 (0%) |


### Revenue Drivers
- Revenue share by specialization: Pediatrics **46.91%**, Dermatology **35.13%**, Oncology **17.95%**

- Top treatment types by revenue: **Chemotherapy** ranks #1, followed by imaging/diagnostics (X-Ray, MRI, ECG) 


### Risk Exposure
- Revenue concentration: **Top 5 doctors generate ~60% of total revenue**

- Highest volatility (provider-level): doctors such as **D008** and **D005** show the widest monthly revenue ranges


### Patient Behavior (SQL-only Segmentation)
- Chronic high-frequency patients: **20**
- Frequent low-cost patients: **16**
- Other patients: **12**


### Temporal Patterns
- Demand peak: **April (50 appointments)**  
- Lowest demand: **September (22 appointments)**  
- Revenue peak: **April (~592K)**; weakest: **August (~291K)**  
- MoM analysis shows cyclical growth/decline and occasional divergence between volume vs value.

---

## ✅ Executive Summary

---

## 🧠 Management Recommendations

---

## ▶️ How to Run
1) Load CSV files into SQLite and create the database schema.  
2) Run `sql/00_create_views.sql` to generate working views.  
3) Run analysis queries from the `sql/` folder or read details in `docs/`.

---

