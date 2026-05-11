# Azure Data Engineering with Databricks
## Formula 1 End-to-End Azure Data Engineering Project## 🏎️ Project Overview
This project builds a production-grade data pipeline using the Medallion Architecture. It automates the process of ingesting Formula 1 motor racing data from the Ergast API, transforming it into a structured format, and preparing it for analytical reporting.
## 🏗️ Architecture Diagram

Ergast API ➡️ Azure Data Factory ➡️ Azure Data Lake (Bronze) ➡️ Databricks (Silver) ➡️ Databricks (Gold)
## 🛠️ Tech Stack

* Cloud Provider: Microsoft Azure
* Orchestration: Azure Data Factory (ADF)
* Data Lake: Azure Data Lake Storage (ADLS) Gen2
* Processing Engine: Azure Databricks (PySpark)
* Storage Format: Delta Lake
* Language: Python (PySpark) & SQL

## 📂 Medallion Layers

   1. Bronze (Raw): Landed raw JSON/CSV data from the API into ADLS using ADF.
   2. Silver (Processed): Cleaned data types, handled nulls, and applied schema enforcement using Databricks.
   3. Gold (Presentation): Joined multiple tables (Drivers, Results, Circuits) to create business-level aggregates for analysis.

## 🚀 Key Features

* Incremental Loading: Built pipelines to only process new race data rather than re-processing everything.
* Automation: Used Azure Data Factory to trigger Databricks notebooks in a specific sequence.
* Unity Catalog/Mounting: Implemented secure storage access between Databricks and Azure.

## 📈 How to Run

   1. Azure Setup: Create a Resource Group, ADLS Gen2, Databricks Workspace, and ADF Instance.
   2. Mounting: Run the 0.mount_storage notebook to link Databricks to your storage.
   3. Ingestion: Trigger the ADF pipeline to pull data from the Ergast API.
   4. Transformation: Run the notebooks in the trans folder to move data from Silver to Gold.


