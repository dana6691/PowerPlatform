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
 
## Apache Spark
  - open source parallel processing framework for large-scale data processing and analytics. large volumes of data quickly by distributing the work across multiple computers. RUn code Java/Scala/Spark R/Spark SQL/PySpark. each workspace in MS Fabric is assigned a Spark cluster
  - Configuration Settings
    - Node Family: type of virtual machines used for the Spark cluster nodes. (memory optimized)
    - Runtime version
    - Spark Properties
- Run Spark Code
  - Notebooks: enable you to combine text, images, and code written in multiple languages and collaborate. consist of one or more cells, each of which can contain markdown-formatted content or executable code
  - Spark Job Definition: use Spark to ingest and transform data as part of an automated process(script on demand/based on a schedule)
  - Work with data in Spark Dataframe: (RDD)resilient distributed dataset, common data structure = dataframe, which is provided as part of the Spark SQL library. Saves the dataFrame into a parquet file in the data lake
  - Work with data using Spark SQL
  - Visualize data in a Spark Notebook: using built-in notebook charts/using graphics packages in code

## Delta Lake Tables
  - Tables in lakehouse are based on the Delta Lake storage format, commonly used in Apache Spark. enables relational database capabilities for batch and streaming data. can implement a lakehouse architecture to support SQL-based data manipulation semantics
  - Delta Lake
    - an open-source storage layer that adds relational database semantics to Spark-based data lake processing.

## Data Factory pipelines
- a sequence of activities that orchestrate an overall process, usually by extracting data from one or more sources and loading it into a destination; often transforming. To automate extract, transform, and load (ETL) processes that ingest transactional data from operational data stores into an analytical data store,
- Concepts
  - Activities: executable tasks in a pipeline. 1) Data transformation 2) Control flow
  - Parameters
  - Pipeline Runs
- Copy Data Activity: Ingest data from an external source into a lakehouse file or table.
  - If you need to transform the data or use multiple sources, use Data Flow activity to run a dataflow (Gen2). use the Power Query user interface to define a dataflow (Gen2)  

## Ingest Data with Dataflows Gen2
- Dataflows: a type of cloud-based ETL (Extract, Transform, Load) tool for building and executing scalable data transformation processes.
- Dataflows (Gen2): used to ingest and transform data from multiple sources, and then land the cleansed data to another destination. Using Power Query Online also allows for a visual interface 
- Create Dataflow 1) Data Factory workload 2) Power BI workspace 3) directly in the lakehouse
  

## Get started with data warehouses in Microsoft Fabric
Microsoft Fabric enables data engineers and analysts to ingest, store, transform, and visualize data all in one tool with both a low-code and traditional experience.
- Fabric's data warehouse
  - a relational data warehouse that supports the full transactional T-SQL capabilities
  - use Spark to process the data and create machine learning models.
- Tables
  - Fact tables: contain the numerical data that you want to analyze. Primary source
  - Dimension tables: contain descriptive information about the data
- Schema
  - Star: a mature modeling approach widely adopted by relational data warehouses. a fact table is directly related to the dimension tables,
  - Snowflake:
1) Describe a data warehouse in Fabric
  - create your data warehouse directly in Fabric from the create hub or within a workspace.
  - Fabric's Lakehouse is a collection of files, folders, tables, and shortcuts that act like a database over a data lake.
  - https://learn.microsoft.com/en-us/training/modules/get-started-data-warehouse/3-understand-data-warehouse-fabric
  - ?

2) Ingest data into your data warehouse
3) Query and Transform
- Query
  - using SQL query editor
  - using the Visual query editor
4) Prepare and visualize data
  - Model view: Build relationships & Create measures using DAX & hide fields
  - Understand the default dataset
  - Visualize
5) Secure and monitor your data warehouse
  - Security
    -   Role-based access control (RBAC)
    -   SSL encryption to secure the communication between the warehouse and the client applications.
    -   Azure Storage Service Encryption to protect the data in transit and at rest.
    -   Azure Monitor and Azure Log Analytics to monitor the warehouse activity and audit the access to the data.
    -   Multifactor authentication (MFA) to add an extra layer of security to user accounts.
    -   Azure Active Directory (Azure AD) integration to manage the user identities and access to the warehouse. 
  - Monitor: *dynamic management views (DMVs)* to monitor connection, session, and request status to see live SQL query lifecycle
  - Query monitoring
## Data Science
- Machine Learning
  - Classification: predict a categorical value
  - Clustering: group together with similar data points
  - Regression: predict a numerical value
  - Forecasting: predict future numerical value based on the time-series model
-  Process  
  - Define problem > get data > prepare data > train the model > generate insight
1) Ingest and orchestrate data from multiple sources (local/cloud), can save data into MS Fabric *lakehouse*. Any structured, semi-structured, and unstructured files
2) Transform data
  - most familiar with writing and executing code in notebooks
  - Prepare your data with the Data Wrangler
3) Train and score models
  - Start tracking metrics
4) Review result
  -  MLflow in a notebook to review tracked metrics
  -  Microsoft Fabric's experiments offers a visual user interface to explore the metrics.


