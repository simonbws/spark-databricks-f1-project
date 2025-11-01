# Set-Up Notebooks

This folder contains notebooks to configure the environment for the **F1 Data Engineering** project in Databricks and to connect to **Azure Data Lake Storage Gen2 (ADLS)**.

## Notebooks

### 1. Access Azure Data Lake using Service Principal
- Retrieves `client_id`, `tenant_id`, and `client_secret` from **Azure Key Vault**.
- Sets up Spark configurations for **OAuth authentication**.
- Test the connection and explore files in ADLS.

### 2. Mount ADLS using Service Principal
- Mounts a single ADLS container to DBFS using the Service Principal.
- Provides access to project data in paths like:  
  `/mnt/<storage_account>/<container_name>`
- Used to mount the main project containers: `raw`, `processed`, `presentation`.

### 3. Mount ADLS Containers for the Project
- Contains a `mount_adls()` function that mounts all project containers automatically.
- Checks if a container is already mounted and unmounts it before remounting if needed.
- Mounts all necessary containers (`raw`, `processed`, `presentation`) so all notebooks can read and write data.

## Usage
- Run these notebooks **before any ingestion or transformation notebooks** to ensure data is accessible.
- After mounting, all paths like `/mnt/formula1projectdls/raw/` are available in Spark.
- These setup steps are essential for the pipeline workflow:  
  **ingestion → transformations → presentation → analysis**
