
# fhir-medallion-lakehouse-fabric-project
End-to-end FHIR data ingestion and analytics pipeline using Microsoft Fabric. Implements Medallion Lakehouse architecture (Raw, Bronze, Silver, Gold) with incremental ingestion, SCD Type 2 versioning, and pipeline orchestration.
________________________________________________
# FHIR Data Ingestion & Analytics Assignment

##  Tools Used
- FHIR API
- Microsoft Fabric
- PySpark 


##  Architecture
Raw → Bronze → Silver → Gold

##  Pipeline Flow
Patient → Encounter → Observation → Condition

##  Data Ingestion
- Used FHIR API with pagination
- Stored raw JSON in Lakehouse

##  Bronze Layer
- Converted raw JSON to Delta tables

##  Silver Layer
- Flattened nested JSON
- Extracted important fields
- Removed duplicates

##  Gold Layer
- Created analytics-ready tables

##  SCD Type 2
- Implemented using MERGE
- Tracks historical changes

##  Output
- Clean structured tables ready for reporting

##  Screenshots
Refer "/screenshots" folder

##  How to Run
1. Open notebook in Microsoft Fabric
2. Run all cells
3. Execute pipeline
