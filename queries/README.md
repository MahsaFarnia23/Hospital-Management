This folder contains all SQL scripts used in the Hospital Management Analytics project.
Queries are grouped by business purpose and written for **SQLite**.

----
## Doctor Performance & Capacity (Operational Analytics)
### Doctor Ranking by Workload (Monthly)

| Doctor ID | First Name | Last Name | Specialization | Month | Appointment Count | Workload Rank |
|---|---|---|---|---|---:|---:|
| D001 | David | Taylor | Dermatology | 2023-01 | 3 | 1 |
| D004 | David | Jones | Pediatrics | 2023-01 | 3 | 1 |
| D003 | Jane | Smith | Pediatrics | 2023-01 | 2 | 3 |
| D005 | Sarah | Taylor | Dermatology | 2023-01 | 2 | 3 |
| D006 | Alex | Davis | Pediatrics | 2023-01 | 2 | 3 |

Monthly doctor ranking shows persistent workload concentration, with the same providers, mainly in Pediatrics and Dermatology, frequently occupying top ranks.
While leadership rotates month to month, overload and underutilization coexist, indicating inefficient appointment allocation.
This pattern suggests a structural scheduling imbalance, increasing burnout risk and limiting effective capacity use.

### Workload Variance Within Specializations

| Specialization | Month | Avg. Appointments per Doctor | Workload Range |
|---|---|---:|---:|
| Pediatrics | 2023-01 | 1.80 | 2 |
| Dermatology | 2023-01 | 2.33 | 1 |
| Oncology | 2023-01 | 2.00 | 0 |
| Dermatology | 2023-02 | 2.00 | 2 |
| Pediatrics | 2023-02 | 1.20 | 1 |


Pediatrics shows the highest workload variance, indicating significant imbalance among doctors within the same specialization.
Dermatology exhibits moderate but recurring variance, suggesting periodic provider overload.
Oncology remains consistently balanced, with minimal variance and predictable workload distribution.

### Total Appointments by Specialization

| Specialization | Total Appointments |
|---|---:|
| Pediatrics | 98 |
| Dermatology | 70 |
| Oncology | 32 |

Pediatrics dominates appointment demand, indicating the highest operational workload.
Dermatology shows steady demand, while Oncology operates at substantially lower volume, requiring less scheduling capacity.

[Doctor_Performance_Capacity](Doctor_Performance_Capacity.sqbpro)

----
## Revenue Intelligence 
### Revenue by Doctor 

| Doctor ID | First Name | Last Name | Specialization | Total Revenue |
|---|---|---|---|---:|
| D005 | Sarah | Taylor | Dermatology | 394,356.89 |
| D006 | Alex | Davis | Pediatrics | 339,280.84 |
| D001 | David | Taylor | Dermatology | 336,851.92 |
| D010 | Linda | Wilson | Oncology | 304,846.08 |
| D003 | Jane | Smith | Pediatrics | 279,957.14 |

Hospital revenue is highly concentrated among a small number of doctors, with the top few providers contributing a disproportionate share of total revenue.
This concentration creates dependency and staffing risk, making retention and workload management of top earners strategically critical.

### Revenue by Specialization

| Specialization | Total Revenue |
|---|---:|
| Pediatrics | 1,289,294.61 |
| Dermatology | 965,566.84 |
| Oncology | 493,428.71 |

Pediatrics is the dominant revenue driver, generating the highest total revenue, followed by Dermatology with a strong but secondary contribution.
Oncology contributes significantly less in total revenue, indicating lower volume despite its clinical importance.
### Revenue per Appointment by Specialization

| Specialization | Appointment Count | Total Revenue | Revenue per Appointment |
|---|---:|---:|---:|
| Oncology | 32 | 493,428.71 | 15,419.65 |
| Dermatology | 70 | 965,566.84 | 13,793.81 |
| Pediatrics | 98 | 1,289,294.61 | 13,156.07 |

Oncology delivers the highest revenue per appointment, indicating low-volume but high-value care.
Pediatrics relies on volume rather than value, while Dermatology balances moderate volume with strong per-visit revenue efficiency.

### Monthly Revenue by Doctor

| Doctor ID | First Name | Last Name | Month | Monthly Revenue |
|---|---|---|---|---:|
| D001 | David | Taylor | 2023-01 | 48,610.78 |
| D001 | David | Taylor | 2023-02 | 32,150.83 |
| D001 | David | Taylor | 2023-03 | 38,666.04 |
| D001 | David | Taylor | 2023-04 | 48,958.15 |
| D001 | David | Taylor | 2023-05 | 26,056.66 |

Monthly doctor revenue is highly uneven and volatile, with several providers showing sharp spikes and low months rather than stable performance.
This pattern indicates revenue dependency on episodic high-value cases and a subset of doctors, increasing forecasting and staffing risk.

### Monthly Revenue by Specialization 

| Specialization | Month | Monthly Revenue |
|---|---|---:|
| Dermatology | 2023-01 | 85,165.21 |
| Dermatology | 2023-02 | 77,187.39 |
| Dermatology | 2023-03 | 89,033.39 |
| Dermatology | 2023-04 | 76,462.00 |
| Dermatology | 2023-05 | 43,350.22 |

Monthly revenue patterns vary by specialization: Pediatrics delivers the highest and most consistent revenue, while Dermatology shows clear seasonal peaks, especially mid-year.
Oncology is the most volatile, with sharp spikes and drops, indicating reliance on episodic high-value treatments rather than steady demand.

### Revenue Volatility by Specialization

| Specialization | Avg. Monthly Revenue | Revenue Range |
|---|---:|---:|
| Pediatrics | 107,441.22 | 111,867.68 |
| Dermatology | 80,463.90 | 96,290.88 |
| Oncology | 41,119.06 | 90,574.55 |

Pediatrics has the highest average monthly revenue but also the largest revenue range, indicating strong performance with notable volatility.
Dermatology and Oncology show lower averages but still meaningful variability, highlighting the need for specialization-specific staffing and revenue risk management.

[Revenue_Intelligence](Revenue_Intelligence.sqbpro)

----
## Patient Behavior 

### Patient-Level Metrics

| Patient ID | Visit Count | Total Spend | Last Visit Date |
|---|---:|---:|---|
| P001 | 8 | 61,752.56 | 2023-04-09 |
| P002 | 6 | 35,812.44 | 2023-10-06 |
| P003 | 4 | 31,747.52 | 2023-08-26 |
| P004 | 4 | 21,450.04 | 2023-07-07 |
| P005 | 16 | 297,758.56 | 2023-11-14 |

Patient behavior is highly uneven in terms of visit frequency and total spending, with a small subset of patients accounting for a disproportionate share of overall costs.
This pattern provides a strong foundation for patient segmentation and identifying high-cost or operationally intensive patient groups.

[Patient-Level Metrics](Patient-Level_Metrics.sqbpro)

----

## Time-based Patterns

### Seasonality Detection (Appointments & Revenue)

Appointments and revenue both show clear seasonal patterns, peaking in spring (especially April) and reaching their lowest levels in late summer (August–September).
Revenue varies more sharply than appointment volume, indicating that financial performance is driven by seasonal changes in treatment mix, not just the number of visits.

| Month (MM) | Appointment Count |
|---|---:|
| 01 | 40 |
| 02 | 28 |
| 03 | 38 |
| 04 | 50 |
| 05 | 38 |


| Month (MM) | Revenue |
|---|---:|
| 01 | 519,533.00 |
| 02 | 337,485.38 |
| 03 | 488,992.90 |
| 04 | 592,871.50 |
| 05 | 569,006.50 |

[Seasonality Detection](Seasonality_Detection.sqbpro)

----
