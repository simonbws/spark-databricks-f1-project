### Azure Data Factory (ADF)
**Azure Data Factory (ADF)** is used to automate and schedule Databricks pipelines.

### Pipelines
1. pl_ingest_formula1_data — runs ingestion notebooks  
2. pl_transform_formula1_data — runs transformation notebooks  
3. pl_process_formula1_data — combines ingestion and transformation into a single end-to-end process  

### Linked Services
- ls_formula1dl_storage — connection to Azure Data Lake Storage (ADLS)  
- ls_databricks_project_ws — connection to the Databricks workspace  

### Trigger
- tr_process_f1_data — runs the full data process **weekly** (every 168 hours)

---

## Data Flow (ETL)

### Extract (ADF)
- ADF retrieves source data from the **Ergast API**  
- Checks and creates raw folders in ADLS: `/raw/YYYY-MM-DD`

### Transform (Databricks)
- **Spark notebooks** load, clean, and join datasets  
- Processed data is stored in `/processed`

### Load (e.g., Power BI for Visual Analytics)
- The data model from `/presentation` is used for **Power BI dashboards and reports**

---

### Schedule
The ADF trigger `tr_process_f1_data` ensures the full data pipeline runs automatically every week.
