#  FHIR Medallion Lakehouse Data Engineering Project

##  Overview
This project implements an end-to-end data engineering pipeline using the FHIR public API to build a scalable Medallion Lakehouse architecture in Microsoft Fabric.

It ingests healthcare data, processes it through multiple layers, and prepares it for analytics and reporting.

________________________

##  Tech Stack
- Microsoft Fabric (Lakehouse, Notebook, Pipeline)
- PySpark
- FHIR REST API
- Delta Lake
- GitHub

________________________

##  Architecture
Medallion Architecture:

Raw → Bronze → Silver → Gold

________________________

##  Data Pipeline Flow
Patient → Encounter → Observation → Condition

________________________

##  Data Ingestion
- Extracted data from FHIR API using pagination
- Implemented incremental ingestion (multi-run simulation)
- Stored raw JSON responses in Lakehouse (date-partitioned)
- Added metadata columns:
  - extraction_timestamp
  - api_url
  - load_date

________________________

##  Bronze Layer
- Converted raw JSON into structured Delta tables
- Maintains original structure for traceability

________________________

##  Silver Layer
- Flattened nested FHIR JSON (entry → resource)
- Extracted meaningful attributes
- Removed duplicates
- Cleaned and standardized data

________________________

##  Gold Layer
- Created analytics-ready tables:
  - gold_patient
  - gold_encounter
- Optimized for reporting and BI tools

________________________

##  SCD Type 2 Implementation
- Implemented Slowly Changing Dimension Type 2
- Tracks historical changes in patient data
- Maintains:
  - effective_from
  - effective_to
  - is_current flag

________________________

##  Pipeline Orchestration
- Built using Microsoft Fabric Data Pipeline
- Automates:
  - Data ingestion
  - Transformation
  - Data loading
  - Logging

________________________

##  Output
- Clean structured data for analytics
- Ready for Power BI reporting

________________________

##  Screenshots

### Raw Layer Tables
![Raw Data Ingestion](screenshots/Raw_Layer_Data_Ingestion.png)
![Raw Tables](screenshots/Raw_Layer_Tables.png)

### Bronze Layer Tables
![Bronze Table](screenshots/Bronze_Layer_Table.png)

### Silver Layer Tables
![Silver Table](screenshots/Silver_Layer_Table.png)
![Silver Tables](screenshots/Silver_Layer_Tables.png)

### Gold Layer Tables
![Gold Table](screenshots/Gold_Layer_Table.png)
![Gold Tables](screenshots/Gold_Layer_Tables.png)

### SCD Type2 Implementation
![SCD Table](screenshots/SCD_Type2_Table.png)
![Spark Job Graph](screenshots/SparkApplication&JobGraph.png)

### Monitor Logging Tables
![Logging Table](screenshots/Monitor_Logging_Table.png)
![Logging Tables](screenshots/Monitor_Logging_Tables.png)

### Pipeline Execution
![Pipeline](pipeline/FHIR_Data_Pipeline _Status_Success.png)

________________________


##  How to Run
1. Open notebook in Microsoft Fabric
2. Run all notebook cells
3. Execute pipeline for orchestration

________________________

##  Repository Structure
