# Formula 1 Data Engineering Project — Databricks & Spark

This project presents a complete data engineering pipeline built with Azure Databricks, Apache Spark, and Delta Lake. It focuses on processing and analyzing Formula 1 race data retrieved from the Ergast Developer API (https://ergast.com/mrd/).

The goal of this project is to demonstrate how to design a modern data lakehouse pipeline using Azure Databricks, with a focus on core Apache Spark concepts, data ingestion, and integration with Azure Data Lake Storage Gen2.

---

## ⚙️ Project Overview

The pipeline follows the **medallion architecture**:

**Raw → Ingestion → Processed → Presentation → Analysis**

- **Ingestion:** Load raw data (CSV/JSON) from the Ergast dataset into Delta tables.  
- **Processed:** Clean, transform, and join data from multiple sources using Apache Spark.  
- **Presentation:** Create curated tables such as calculated_race_results for analytics and reporting. 
- **Analysis:** Leverage Spark SQL to explore the data and identify dominant Formula 1 drivers and teams across different seasons.  

The result is a fully automated pipeline that produces season-level insights and supports fast, ad-hoc exploration through SQL queries.

---

## 🧩 Data Source

Data comes from the **Ergast Developer API**, which provides open historical Formula 1 data. 
For educational purposes, data can be used under their terms of use (https://ergast.com/mrd/terms/).

📦 Download data: [https://ergast.com/mrd/db/](https://ergast.com/mrd/db/)

Main datasets include:
- `circuits.csv`
- `races.csv`
- `drivers.json`
- `constructors.json`
- `results.json`
- `pit_stops.json`
- `lap_times.csv`
- `qualifying.json`

---

## 🚀 How to Run

1. **Download Ergast data** and upload it to Azure Data Lake or local `/data/raw`
2. **Create Databricks databases:**
   - `f1_raw`
   - `f1_processed`
   - `f1_presentation`
3. **Run notebooks** in order:
   1. Ingestion  
   2. Processed  
   3. Presentation  
   4. Analysis  
4. **Explore results** in the `analysis` notebook (SQL insights and visualizations)

---

## 🛠️ Technologies Used

- **Azure Databricks** — compute and orchestration  
- **Apache Spark (PySpark & Spark SQL)** — distributed data processing  
- **Delta Lake** — ACID data storage  
- **Azure Data Lake Storage Gen2** — data lake layer  
- **Azure Data Factory** — simple pipeline orchestration

---
#### Author simonbws
This project is based on a Udemy data engineering course and was recreated to deepen my understanding of Apache Spark, Azure Databricks, and data lakehouse architecture.
#### [View the Certificate of Completion] https://www.udemy.com/certificate/UC-595a172d-5bb5-4bdf-b37b-bd7d65a1d25a/
