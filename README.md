# Azure Databricks Lakehouse Pipeline

An end-to-end data engineering project built using **Azure Databricks, PySpark, Delta Lake, and Unity Catalog**. Implements the Medallion Architecture to ingest, transform, validate, and process data into analytics-ready datasets.

## Architecture

The project follows the **Bronze → Silver → Gold** Medallion Architecture.

```text
       Source Data
            |
            v
    Azure Data Lake Storage
            |
            v
     +--------------+
     |    BRONZE    |
     | Raw Ingestion|
     | Delta Tables |
     +--------------+
            |
            v
     +--------------+
     |    SILVER    |
     | Data Cleaning|
     | Transformations
     | Delta Tables |
     +--------------+
            |
            v
     +--------------+
     |     GOLD     |
     | Data Quality |
     | Fact & Dimension
     | SCD Type 1 & 2|
     +--------------+
            |
            v
     Analytics-Ready Data
```

## Technology Stack

- **Cloud:** Microsoft Azure
- **Data Processing:** Azure Databricks, PySpark
- **Storage:** Azure Data Lake Storage Gen2, Delta Lake
- **Data Governance:** Unity Catalog
- **Pipeline Development:** Lakeflow Spark Declarative Pipelines
- **Change Processing:** Structured Streaming, Auto CDC
- **Programming:** Python, SQL
- **Version Control:** Git, GitHub

## Pipeline Implementation

### Bronze Layer – Data Ingestion
- Ingest raw source datasets into ADLS Gen2.
- Implement incremental data ingestion.
- Store raw data in Delta format.

### Silver Layer – Data Transformation
- Clean and transform data using PySpark.
- Handle missing values and invalid records.
- Apply schema and data type transformations.
- Validate and maintain data consistency.

### Gold Layer – Dimensional Modelling
- Build fact and dimension tables.
- Implement SCD Type 1 and Type 2.
- Use Lakeflow Auto CDC for change processing.
- Apply data quality expectations.
- Maintain historical records for analytical use cases.

## Key Concepts

- Medallion Architecture
- Incremental Data Ingestion
- Apache Spark Structured Streaming
- Delta Lake
- PySpark DataFrame Transformations
- Lakeflow Spark Declarative Pipelines
- Data Quality Expectations
- Auto CDC
- Slowly Changing Dimensions (SCD Type 1 & 2)
- Dimensional Data Modelling
- Unity Catalog

## Azure Infrastructure

- Azure Databricks Workspace
- Azure Data Lake Storage Gen2
- Azure Databricks Access Connector
- Unity Catalog Storage Credentials
- External Locations and Managed Identity Authentication

## Running the Project

1. Set up an Azure Databricks workspace and ADLS Gen2 storage account.
2. Configure the Databricks Access Connector and required Azure IAM permissions.
3. Configure Unity Catalog storage credentials and external locations.
4. Import the project notebooks into Databricks.
5. Configure storage paths, catalogs, and schemas.
6. Execute the notebooks and Lakeflow pipeline.

## Repository Structure

```text
azure-databricks-lakehouse-pipeline/
│
├── Datasets/
├── Notebooks/
└── README.md
```

---

**Author:** [gowsalyanagaraj](https://github.com/gowsalyanagaraj)
