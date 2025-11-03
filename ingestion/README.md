# Ingestion Layer

The **ingestion** folder handles the first stage of the Formula 1 Data Engineering pipeline.  
Its purpose is to **extract and transform raw data** from the `f1_raw` layer into a structured form in the `f1_processed` database.

Data is read from the raw container in Azure Data Lake Storage, cleaned, enriched with metadata, and stored in Delta format using Apache Spark in Databricks.

---

## Folder Contents

- **create_processed_database** — creates the `f1_processed` database in the ADLS `/processed` container.  
- **ingest_all_files** — the main orchestration notebook that runs all ingestion notebooks in sequence.  
- Each ingestion notebook:
  - reads data from `/raw/`,
  - performs cleaning and validation,
  - adds metadata columns (`data_source`, `file_date`, `ingestion_date`),
  - writes the processed data into `f1_processed` in Delta format.

---

## ADLS Integration

Mounted paths in Databricks:

/mnt/formula1projectdls/raw/
/mnt/formula1projectdls/processed/
/mnt/formula1projectdls/presentation/

Spark configuration and container mounting are handled by the notebooks in the **set-up** folder (`mount_adls_containers_for_project`).

---

## Data Flow

1. Source: (https://ergast.com/mrd/) (CSV/JSON).  
2. RAW layer → `/mnt/formula1projectdls/raw/`  
3. Processing → ingestion notebooks (Spark SQL + Delta).  
4. Output → `f1_processed` database in `/mnt/formula1projectdls/processed/`.

---

## Purpose

To create data layer  for the next stages of the pipeline: transformations → presentation → analysis.
