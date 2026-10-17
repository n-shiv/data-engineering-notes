# Module 2 - Data Engineering Ecosystem

## 🌐 Data Engineering Ecosystem

A Data Engineer works with tools and technologies to:

-   Collect data from multiple sources
-   Build ETL/ELT pipelines
-   Store data efficiently
-   Process & transform data
-   Deliver analytics-ready data

### Core Components

-   Data Sources
-   Data Repositories
-   ETL / ELT
-   Data Pipelines
-   Programming Languages
-   Big Data Frameworks
-   BI & Reporting Tools

------------------------------------------------------------------------

# 📊 Types of Data

## Structured Data

-   Fixed schema
-   Stored in rows & columns
-   Easy to query using SQL

**Examples** - SQL Databases - Excel - Transaction Records

## Semi-Structured Data

-   No fixed schema
-   Uses metadata/tags

**Examples** - JSON - XML - Emails

## Unstructured Data

-   No predefined structure

**Examples** - Images - Videos - PDFs - Social Media - Audio

------------------------------------------------------------------------

# 📂 Common File Formats

## 📂 Common File Formats

| Format | Best Used For | Description |
|--------|---------------|-------------|
| **CSV** | Tabular data exchange | Stores data as comma-separated values; widely used for importing/exporting datasets. |
| **TSV** | Data containing commas | Similar to CSV but uses tabs as separators, avoiding issues with commas in data. |
| **XLSX** | Spreadsheet analysis | Microsoft Excel format supporting multiple sheets, formulas, charts, and formatting. |
| **JSON** | APIs & Web Services | Lightweight key-value format commonly used for data exchange between applications. |
| **XML** | Data exchange | Tag-based format for storing and transporting structured data. |
| **PDF** | Documents | Portable document format used for sharing reports while preserving layout. |

------------------------------------------------------------------------

# 🔗 Data Sources

-   **Internal:** Relational DBs, Data Warehouses, ERP, CRM
-   **External:** APIs, Web Services, Government Datasets, Third-party
    Data
-   **Real-time:** IoT, Sensors, GPS, Social Media, Clickstreams
-   **Collection:** API Integration, Web Scraping, Streaming, RSS Feeds

------------------------------------------------------------------------

# 💾 Data Repositories

## Database

Stores operational data.

Examples: MySQL, PostgreSQL, Oracle, SQL Server

## Data Warehouse

-   Clean, transformed, analytics-ready data
-   Historical data
-   BI Reporting
-   OLAP
-   Single Source of Truth

Examples: Snowflake, Amazon Redshift, BigQuery

## Data Mart

Department-specific subset of a Data Warehouse.

## Data Lake

Stores raw structured, semi-structured and unstructured data.

Examples: Amazon S3, Hadoop

------------------------------------------------------------------------

------------------------------------------------------------------------

# 📝 What is a Schema?

A **schema** defines **how data is organized and structured** in a
database or data repository.

Think of it as a **blueprint** that specifies: - Table names - Column
names - Data types - Relationships between tables - Constraints (Primary
Key, Foreign Key, NOT NULL, etc.)



### Example: Customer Table

| Customer_ID | Name  | Email |
|------------:|-------|-------------------|
| 101 | Alice | alice@email.com |

**Schema**

-   `Customer_ID` → Integer (Primary Key)
-   `Name` → VARCHAR(100)
-   `Email` → VARCHAR(255)

### Schema Types

#### Schema-on-Write (Data Warehouse)

-   Schema is defined **before** data is loaded.
-   Data must match the predefined structure.
-   Ensures high data quality and fast analytical queries.

#### Schema-on-Read (Data Lake)

-   Raw data is stored first.
-   Schema is applied **when data is read**.
-   Supports structured, semi-structured, and unstructured data.
-   Ideal for exploratory analytics and Machine Learning.

### Key Takeaway

-   **Structured data** → Fixed schema
-   **Semi-structured data** → Partial/Flexible schema (e.g., JSON, XML)
-   **Unstructured data** → No predefined schema

# SQL vs NoSQL

## SQL

-   Fixed Schema
-   ACID Compliance
-   Strong Consistency
-   Complex Joins

## NoSQL

-   Flexible Schema
-   High Scalability
-   High Performance
-   Big Data Support

**Types** - Key-Value → Redis, DynamoDB - Document → MongoDB, CouchDB -
Column → Cassandra, HBase - Graph → Neo4j, CosmosDB

------------------------------------------------------------------------

# 🔄 ETL vs ELT

## ETL

Extract → Transform → Load

Best for Data Warehouses.

## ELT

Extract → Load → Transform

Best for Data Lakes and Big Data.

------------------------------------------------------------------------

# 🚀 Data Pipeline

Moves data from source to destination.

Modes: - Batch - Streaming - Hybrid

Tools: - Apache Airflow - Apache Beam - Google Dataflow

------------------------------------------------------------------------

# 🧩 Metadata

**Metadata = Data about Data**

Metadata describes the characteristics, structure, and context of data, making it easier to manage, search, and understand.

### Technical Metadata
Describes the technical structure of data.
- Table and column names
- Data types
- Primary/Foreign keys
- File format and schema

### Process Metadata
Describes how data is created and processed.
- ETL job details
- Data lineage (source → destination)
- Execution time
- Processing logs and status

### Business Metadata
Provides business context for data.
- Business definitions
- KPIs and metrics
- Data owner
- Business rules and documentation

> **Example:** A `Customer_ID` column may have:
> - **Technical Metadata:** Integer, Primary Key
> - **Process Metadata:** Loaded daily from CRM via ETL
> - **Business Metadata:** Unique identifier for each customer

------------------------------------------------------------------------

# 💻 Programming Languages

-   SQL
-   Python
-   Java
-   R
-   Bash
-   PowerShell

------------------------------------------------------------------------

# 🌍 Big Data (5 Vs)

- **Volume** – The massive amount of data generated and stored every day.
- **Velocity** – The speed at which data is generated, processed, and analyzed.
- **Variety** – The different types and formats of data (structured, semi-structured, and unstructured).
- **Veracity** – The quality, accuracy, and reliability of the data.
- **Value** – The useful insights and business benefits derived from data.

------------------------------------------------------------------------

# ⚡ Big Data Technologies

## Hadoop

-   Distributed Storage
-   HDFS
-   Fault Tolerant

## Hive

-   SQL on Hadoop
-   Data Warehousing

## Spark

-   In-memory Processing
-   Real-time Analytics
-   Machine Learning

------------------------------------------------------------------------

# 🛠 Common Data Engineering Tools

-   PostgreSQL
-   MySQL
-   MongoDB
-   Cassandra
-   Kafka
-   Apache Airflow
-   AWS Glue
-   Talend
-   BeautifulSoup
-   Scrapy
-   Git
-   GitHub

------------------------------------------------------------------------

# ⭐ Key Takeaways

-   Data can be Structured, Semi-Structured or Unstructured.
-   Choose repositories based on use case.
-   ETL transforms before loading; ELT transforms after loading.
-   Data Warehouses store processed data; Data Lakes store raw data.
-   SQL suits structured data; NoSQL suits scalable flexible workloads.
-   Big Data revolves around the 5 Vs.
-   Data Engineers build reliable pipelines for analytics-ready data.
