# Southern California Economic Indicators Data Pipeline

## 📖 Project Overview
This project is an automated end-to-end data pipeline that extracts regional macroeconomic data (focusing on Orange County and some parts of the Los Angeles area) directly from the Bureau of Labor Statistics (BLS) API. The data is processed, cleaned, and loaded into a centralized relational database (MariaDB/MySQL) to feed into a dashboard.

**The Business Goal:** To break the "manual data gathering bottleneck" using the **Theory of Constraints (TOC)** framework. By automating the Extract, Transform, and Load (ETL) phases, we maximize system throughput, allowing analysts to focus strictly on math/economic forecasting, scenario planning, and business strategy instead of repetitive Excel spreadsheet management.

## 🏗️ Data Architecture & Flow

The pipeline follows a modern ETL architecture:
1. **Extract (API):** Python script calls the BLS v2 API for local metrics (e.g., OC Unemployment, LA Metro CPI, Nonfarm Employment).
2. **Transform (Pandas):** Raw JSON payloads are flattened, normalized, and timestamped.
3. **Load (SQL/MariaDB):** Data is efficiently inserted into a SQL database using `ON DUPLICATE KEY UPDATE` (Upsert) logic to prevent data duplication.
4. **Output (BI/YAML):** A materialized view feeds directly into a visualization dashboard.

```mermaid
graph LR
    A[BLS API v2<br/>(JSON)] -->|Python Script| B(Pandas DataFrame<br/>Data Transformation)
    B -->|PyMySQL Upsert| C[(MariaDB<br/>Central Data Store)]
    C -->|Live Query| D[BI Dashboard<br/>Economic Forecasting]
    classDef default fill:#111,stroke:#00FF88,stroke-width:2px,color:#FFF;
    class A,B,C,D default;

## 📖 Teck Stack
Refer to the Project(ETL FLOW).png

## 📂 Project Structure
socal-economic-etl-pipeline/
│
├── data/
│   ├── sample_output.csv         # Sample of the transformed data
│
├── sql/
│   ├── schema.sql                # SQL commands to create Database(D.B.) tables
│   └── analytics_views.sql       # SQL views to see the data and calculating inflation/wage metrics
│
├── src/
│   ├── bls_api_extractor.py      # Core python script for API extraction
│   ├── db_loader.py              # Script handling the MariaDB connection and upserts
│   └── dashboard_exporter.py     # Script to export YAML config for the dashboard
│
├── .env.example                  # Template for local environment variables
├── requirements.txt              # Python library dependencies
└── README.md                     # Project documentation(this current markdown)

## 🔄 Setup Configuration
1. Install Python 
        ↓
2. Install Git
        ↓
3. Clone GitHub repository (For Guidance)
        ↓
4. Enter project directory
        ↓
5. Create Python virtual environment
        ↓
6. Activate virtual environment
        ↓
7. Install requirements.txt
        ↓
8. Create .env file
        ↓
9. Add BLS API + database credentials
        ↓
10. Create economic_data database
        ↓
11. Run sql/schema.sql
        ↓
12. Run bls_api_extractor.py
        ↓
13. Verify data in MariaDB/MySQL

