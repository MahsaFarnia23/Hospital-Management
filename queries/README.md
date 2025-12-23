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

Monthly doctor ranking shows persistent workload concentration, with the same providers—mainly in Pediatrics and Dermatology—frequently occupying top ranks.
While leadership rotates month to month, overload and underutilization coexist, indicating inefficient appointment allocation.
This pattern suggests a structural scheduling imbalance, increasing burnout risk and limiting effective capacity use.
[Doctor_Ranking](queries/Doctor_Ranking.sqbpro)
