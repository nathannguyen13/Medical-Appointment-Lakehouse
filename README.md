## Project 2 — Data Lakehouse (Capstone)

### Overview
Implements a dimensional Data Lakehouse using the Databricks
Bronze/Silver/Gold architecture, integrating real-time streaming
fact data with reference dimension data from multiple sources.

### Architecture
- **Bronze**: Raw streaming JSON data ingested via Spark Structured Streaming
- **Silver**: Cleansed and joined with dimension reference tables
- **Gold**: Final fact table optimized for analytical queries

### Data Sources
- **Azure SQL Database**: Cloud-hosted relational database
- **MongoDB Atlas**: NoSQL source for dim_slots
- **Databricks DBFS**: CSV files for dim_patients, dim_age_groups

### Star Schema
| Table | Source | Rows |
|---|---|---|
| fact_appointments | Streaming JSON | 111,488 |
| dim_date | Generated | 4,018 |
| dim_patients | CSV | 36,697 |
| dim_slots | MongoDB Atlas | 10,000 |
| dim_age_groups | CSV | 16 |

### How to Run
1. Upload `appointments.csv`, `patients.csv`, `slots.csv` to
   `/Volumes/workspace/default/ds2002_project2/` in Databricks
2. Update Azure SQL and MongoDB credentials in Cell 5
3. Run all cells top to bottom

### Data Source
Medical Appointment Scheduling System from Kaggle:
https://www.kaggle.com/datasets/carogonzalezgaltier/medical-appointment-scheduling-system
