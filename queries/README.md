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

[Doctor_Performance_Capacity](queries/Doctor_Performance_Capacity.sqbpro)

----
## Revenue Intelligence 
### Revenue by Doctor 


### Revenue by Specialization


### Revenue per Appointment by Specialization


### Monthly Revenue by Doctor


### Monthly Revenue by Specialization 


### Revenue Volatility by Specialization

[Revenue_Intelligence](queries/Revenue_Intelligence.sqbpro)

----
## Patient Behavior 
