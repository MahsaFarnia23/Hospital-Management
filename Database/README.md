## 🗂️ Dataset & Tables
**Dataset:** Hospital Management Dataset
The dataset used in this project was sourced from **Kaggle** and originally provided in **CSV format**.  
It was imported into **SQLite** to enable structured, SQL-based analysis.

----
### Dataset Details
- **File name:** ``
- **Source:** [Kaggle — Hospital Management Dataset](https://www.kaggle.com/datasets/kanakbaghel/hospital-management-dataset?utm_source=chatgpt.com&select=treatments.csv)
- **Dataset type:** 
- **Number of rows:** 
- **Number of columns:** 

##Core tables used:
- `appointments` (appointment_date, doctor_id, patient_id, …)
- `doctors` (doctor_id, specialization, …)
- `treatments` (appointment_id, treatment_type, …)
- `billing` (patient_id, amount, …)
- `patients` (patient_id, gender, …)

> **Modeling note (important):** In this dataset, `billing` is linked to **patients** (via `patient_id`) rather than directly to each appointment line item.  
