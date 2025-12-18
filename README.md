# Hospital Management SQL Analytics (SQLite)

A complete end-to-end SQL analytics project using a hospital management dataset.  
This project demonstrates practical data analyst skills in **data modeling assumptions**, **KPI design**, **operational analytics**, **revenue intelligence**, **patient segmentation (SQL-only)**, and **time-based trend analysis**.

---

## 📑 Table of Contents
- [📘 Project Overview](#-project-overview)
- [🎯 Project Objectives](#-project-objectives)
- [💼 Business Problem](#-business-problem)
- [🗂️ Dataset & Tables](#️-dataset--tables)
- [🧩 Key Deliverables](#-key-deliverables)
- [📌 Key Results Snapshot](#-key-results-snapshot)
- [✅ Executive Summary](#-executive-summary)
- [🧠 Management Recommendations](#-management-recommendations)
- [▶️ How to Run](#️-how-to-run)
- [📁 Project Structure](#-project-structure)

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
- `vw_doctor_monthly_performance`
- `vw_specialization_revenue`
- `vw_patient_value_segments`
- `vw_appointment_to_billing_funnel`



---

## 📌 Key Results Snapshot 
- Funnel KPI: Appointment → Treatment conversion **50%**; Treatment → Billing **100%**  


- Revenue share by specialization (Pediatrics / Dermatology / Oncology) 

- Patient segmentation counts (Chronic high-frequency / Frequent low-cost / Other)  


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

