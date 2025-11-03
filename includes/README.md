# Includes Folder

The **includes** folder contains common utilities and configuration settings used across the project.
Its purpose is to centralize reusable functions and paths to make the notebooks cleaner and easier to maintain.

---

## Contents

### Common Functions
- **add_ingestion_date** — adds a column `ingestion_date` with the current timestamp to track when data was ingested.  
- **re_arrange_partition_column** — moves the partition column to the end of the DataFrame to comply with Delta/Parquet best practices.  
- **overwrite_partition** — overwrites a partition in a table dynamically; creates the table if it doesn't exist.  
- **df_column_to_list** — returns a list of distinct values from a DataFrame column.  
- **merge_delta_data** — performs an upsert (merge) into a Delta table; creates the table if it doesn't exist.
