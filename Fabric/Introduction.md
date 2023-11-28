## Introduction
- Microsoft Fabric: All three Data Analytics Products: Power Bi/Azure Data Factory/Azure Synapse under one umbrella,Single Unified software-as-a-service(SaaS) with all my data stored in a single open format in OneLake.
  - OneLake: lake-centric architecture that provides a single, integrated environment for data professionals and the business to collaborate on data projects.
    - combines storage locations across different regions and clouds into a single logical lake, without moving or duplicating data
    - built on top of Azure Data Lake Storage (ADLS) and data can be stored in any format, including Delta, Parquet, CSV, JSON, and more.
    - For tabular data, the analytical engines in Fabric will write data in delta-parquet format and all engines interact with the format seamlessly.
    - OneCopy
      - key component of OneLake that allows you to read data from a single copy, without moving or duplicating data.

## Lakehouse
- Unified platform: combined data lake(flexibility and scalability storage) + data warehouse(SQL-based analytical capabilities)
- built on top of the OneLake scalable storage layer using Delta format tables + uses Apache Spark and SQL compute engines for big data processing.
- Benefit
  - store all data formats
  - use Spark and SQL engines to process large-scale data and support ML and Predictive modeling
  - schema-on-read format, which means you define the schema as needed
  - support ACID (Atomicity, Consistency, Isolation, Durability) for consistency and integrity
  - a single location for data engineers, data scientists, and data analysts to access and use data.
- Mode
  - Lakehouse: add and interact with tables,files and folders in the laekhouse
  - SQL endpoint: use SQL to query the tables and manage
  - *external data without copying it, use shortcut
- Ingest data into a lakehouse
  - Upload
  - Dataflows(Gend2): import and transform data using Power Query Online or load directly into tables in the lakehouse
  - Notebooks: use notebooks in Fabric to ingest and transform data nd load it into tables or files in lakehouse
  - Data Factory Pipelines: Copy data and orchestrate data processing activities, loading results into lakehouse
- Transform and Explore Data
  - Apache Spark: each fabric lakehouse can use Sparks pools through Notebooks or Spark Job Definitions to process the data in files and process data in tables using Scala/PySaprk/Spark SQL
  - SQL Endpoint: each lakehouse includes a SQL endpoint which can *run T-SQL statements to query*
  - Dataflows(Gen2):  you can create a dataflow to perform subsequent transformations through Power Query, and optionally land transformed data back to the Lakehouse.
  - Data Pipelines: Orchestrate complex data transformation logic that operates on data in the lakehouse through a sequence of activities
 
  - ## Apache Spark
  - 
