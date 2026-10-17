# Module 3 – Data Engineering Lifecycle

> Concise notes on data platform architecture, storage, security, data collection, wrangling, querying, performance, and governance.

# 1. 🏗️ Data Platform Architecture

A data platform uses functional layers to move raw data toward useful insights.

## Data Ingestion / Collection
- Connects to source systems and collects data.
- Supports **batch** and **streaming** ingestion.
- Records metadata such as source and batch size.
- Tools mentioned: Apache Kafka, Amazon Kinesis, Google Dataflow.

## Data Storage and Integration
- Stores data for processing and long-term use.
- Integrates data from multiple sources.
- Makes data available for batch and streaming processing.
- Priorities: reliability, scalability, performance, and cost efficiency.

## Data Processing
- Validates, cleans, and transforms data; applies business rules.
- Supports batch and streaming workloads.
- Common tasks: structuring, normalization, denormalization, and data cleaning.

## Analysis and User Interface
- Delivers processed data to analysts, data scientists, business stakeholders, and applications.
- Interfaces include SQL, programming languages, APIs, dashboards, and BI tools.
- Tools mentioned: Tableau, Power BI, Jupyter Notebook, Cognos Analytics.

## Data Pipeline Layer
- Connects and orchestrates work across ingestion, storage/integration, and processing.
- Automates data movement and transformations.
- Tools mentioned: Apache Airflow and Google Dataflow.

---

# 2. 💾 Data Stores and Design Considerations

A **data store / repository** keeps collected and organized data for business operations, reporting, or analysis.

## Choosing a Data Store
Consider:
- **Data type:** structured, semi-structured, or unstructured.
- **Volume and velocity:** how much data arrives and how quickly.
- **Use case:** transactional operations or analytical queries.
- **Workload:** reads, writes, updates, query complexity, and response time.
- **Operations:** scalability, backup, and recovery.
- **Security:** privacy, access controls, and governance.

## Common Repository Types
- **Relational database (RDBMS):** structured, tabular data with a defined schema.
- **NoSQL database:** flexible data models; includes key-value, document, column-family, and graph databases.
- **Data lake:** stores large volumes of raw data in its native format, without requiring a schema upfront.
- **Big data store:** distributes data across machines for large-scale storage and parallel processing.
- **Data warehouse:** stores curated data for reporting and analytics.
- **Data mart:** a focused repository for a particular business area.

## Transactional vs Analytical Systems
- **Transactional (OLTP):** optimized for frequent, fast inserts, updates, deletes, and lookups.
- **Analytical (OLAP):** optimized for complex queries over large volumes of historical data.
- Data usage influences schema design, indexing, partitioning, and normalization.

## Normalization
- Organizes relational data to reduce redundancy and update/insert/delete anomalies.
- Often useful for transactional systems and data integrity.
- Analytical systems may use denormalized structures to simplify queries and improve reporting performance.

## Storage Quality Attributes
- **Performance:** throughput (data processed per unit time) and latency (time to respond).
- **Availability:** data is accessible when required.
- **Integrity:** data remains accurate and protected from corruption or unauthorized changes.
- **Recoverability:** data can be restored after failures or disasters.

---

# 3. 🔐 Data Security

Security should be designed into the data platform from the beginning.

## CIA Triad
- **Confidentiality:** prevent unauthorized access.
- **Integrity:** protect data and systems from improper changes.
- **Availability:** ensure authorized users can access resources when needed.

## Four Security Layers

### Physical Infrastructure Security
- Controls facility access and protects physical equipment.
- Includes authentication, surveillance, backup power, and disaster-aware facility design.

### Network Security
- **Firewalls:** filter network traffic.
- **Network access control:** permits approved devices.
- **Network segmentation:** isolates systems based on security needs.
- **Encryption protocols:** protect data in transit.
- **Intrusion detection/prevention:** identifies or blocks suspicious activity.

### Application Security
- Use threat modeling and secure design/coding practices.
- Test applications for vulnerabilities before deployment.

### Data Security
- **Authentication:** verifies identity.
- **Authorization:** determines what an authenticated user can access.
- **Encryption at rest:** protects stored data.
- **Encryption in transit:** protects data moving between systems (e.g., TLS/HTTPS).
- Monitor access and security events; retain audit trails.
- Apply **least privilege**: users should receive only the access needed for their role.

---

# 4. 📥 Data Collection and Importing

## Common Data Collection Methods
- **SQL / database queries:** retrieve data from relational databases.
- **APIs:** access data exposed by applications, services, and data marketplaces.
- **Web scraping:** extracts selected information from web pages.
- **RSS feeds:** collect updates from websites and news sources.
- **Data streams:** ingest continuous data from sensors, IoT devices, applications, GPS, and social platforms.
- **Data exchanges:** provide data through defined standards, formats, licensing, and governance controls.

## Importing Data
- Load data into a suitable repository so it can be combined, queried, and analyzed.
- Choose tools based on source, data type, volume, destination, and governance needs.
- ETL tools and pipelines can automate ingestion and import.

---

# 5. 🧹 Data Wrangling

**Data wrangling** (or data munging) is the iterative process of exploring, cleaning, transforming, and validating raw data so it is ready for reliable analysis.

## Common Transformations
- **Structuring:** changes data shape or schema to fit the target use case.
- **Join:** combines columns from related tables using a matching condition.
- **Union:** appends rows from compatible datasets.
- **Normalization:** reduces redundancy and inconsistency.
- **Denormalization:** combines data to make analytical queries easier or faster.
- **Data cleaning:** corrects or manages data quality problems.

## Data Profiling
Examines data structure, content, and relationships to identify:
- Missing or null values
- Duplicate records
- Invalid values or unexpected ranges
- Outliers and inconsistent formats

## Common Data Quality Issues
- **Missing values:** remove records, obtain missing information, or impute values when appropriate.
- **Duplicates:** identify and remove repeated records when they are not valid.
- **Irrelevant fields:** exclude data that does not support the use case.
- **Incorrect data types:** convert values to the intended type.
- **Inconsistent formats:** standardize dates, units, capitalization, names, and whitespace.
- **Outliers:** investigate whether values are errors or valid unusual observations before changing them.

## Tools Mentioned
- **Spreadsheets / Power Query:** accessible cleaning and transformation.
- **OpenRefine:** interactive data cleanup and format conversion.
- **Python:** Jupyter Notebook, NumPy, and pandas.
- **R:** dplyr, data.table, and jsonlite.
- Other tools in the notes: Google DataPrep, IBM Data Refinery, Trifacta Wrangler.

---

# 6. 🔎 Querying Data

Common SQL techniques for understanding and analyzing datasets:

```sql
-- Count records
SELECT COUNT(*) FROM customers;

-- Count unique values
SELECT COUNT(DISTINCT dealer_id) FROM sales;

-- Aggregate values
SELECT SUM(amount), AVG(amount), MAX(amount), MIN(amount)
FROM sales;

-- Filter records
SELECT *
FROM sales
WHERE amount BETWEEN 1000 AND 2000;

-- Sort results
SELECT *
FROM sales
ORDER BY purchase_date DESC;

-- Group and aggregate
SELECT postal_code, SUM(amount)
FROM sales
GROUP BY postal_code;
```

## Core Query Concepts
- **COUNT:** counts rows or non-null values, depending on usage.
- **DISTINCT:** returns unique values.
- **SUM / AVG:** calculate totals and averages.
- **MIN / MAX:** find the smallest and largest values.
- **WHERE:** filters rows based on conditions.
- **LIKE:** matches text patterns using wildcards.
- **ORDER BY:** sorts query results.
- **GROUP BY:** groups rows for aggregation.
- **Standard deviation:** measures how spread out numeric values are.

---

# 7. ⚙️ Performance Tuning and Troubleshooting

## Data Pipeline Performance Risks
- Increasing data volumes and workloads.
- Application or task failures.
- Jobs that start late, wait on dependencies, or execute in the wrong order.
- Incompatible tools or software versions.

## Key Metrics
- **Latency:** time taken to complete a request or task.
- **Failure rate:** frequency of unsuccessful operations.
- **Resource utilization:** CPU, memory, storage, and other resource usage.
- **Traffic / throughput:** volume of requests or data processed over time.

## Troubleshooting Workflow
1. Confirm and characterize the issue.
2. Check software versions, recent deployments, and code changes.
3. Inspect logs, metrics, error messages, and resource usage.
4. Isolate whether the issue relates to infrastructure, data, software, or their interaction.
5. Reproduce the problem in a test environment if needed.
6. Validate the root cause and test a fix before production rollout.

## Database Optimization
- **Capacity planning:** allocate resources for current workload and future growth.
- **Indexing:** speeds up lookup by reducing the need to scan every row.
- **Partitioning:** splits large tables into smaller sections to improve manageability and some queries.
- **Normalization:** reduces redundancy and data anomalies.
- **Monitoring and alerting:** track performance and identify issues early.
- **Job-level monitoring:** measure task completion and runtime across pipeline steps.

## Maintenance
- **Time-based:** performed on a fixed schedule.
- **Condition-based:** triggered by a detected issue or performance decline.

---

# 8. 🛡️ Data Governance and Compliance

**Data governance** defines the principles, practices, and processes used to protect data security, privacy, integrity, and proper use throughout its lifecycle.

## Key Concepts
- **Governance:** defines responsibilities, policies, and controls for managing data.
- **Compliance:** demonstrates adherence to applicable laws, regulations, and standards.
- Compliance is continuous and requires people, processes, technology, and auditable records.

## Examples of Regulations and Standards
- **GDPR:** personal data protection in the European Union.
- **CCPA:** consumer privacy law in California.
- **HIPAA:** protects certain health information in the United States.
- **PCI DSS:** security standard for payment-card data.
- **SOX:** includes financial reporting and internal-control requirements.

> Requirements vary by jurisdiction, industry, and the data being processed.

## Governance Across the Data Lifecycle
- **Acquisition:** define purpose, consent or other legal basis, and collect only necessary data.
- **Processing:** document how and why personal data is processed.
- **Storage:** select appropriate locations and security controls.
- **Sharing:** manage third-party access and contractual responsibilities.
- **Retention and disposal:** define retention periods and securely remove data when required.
- Maintain auditable records of data access, processing, sharing, and deletion.

## Common Controls
- **Authentication:** verifies user identity.
- **Authorization / access control:** restricts access by role and privilege.
- **Least privilege:** grants only the access needed to perform a job.
- **Encryption:** protects data at rest and in transit.
- **Data masking:** hides sensitive values in displayed or shared data.
- **Anonymization:** removes the ability to identify individuals when properly implemented.
- **Pseudonymization:** replaces direct identifiers with artificial identifiers; re-identification may still be possible with additional information.
- **Monitoring and alerting:** detects suspicious activity and supports incident response.
- **Data erasure:** securely removes data; ordinary deletion may not eliminate all recoverable copies.

---

# ⭐ Key Takeaways

- A data platform typically includes ingestion, storage/integration, processing, analysis/UI, and pipeline orchestration.
- Choose a data store based on data type, scale, workload, performance, recovery, and security needs.
- Transactional systems prioritize fast operations; analytical systems prioritize complex queries over large datasets.
- Security relies on confidentiality, integrity, and availability, supported by layered controls.
- Data wrangling turns raw data into trustworthy, analysis-ready data.
- **Joins combine columns; unions append rows.**
- Use SQL aggregation, filtering, sorting, and grouping to explore datasets.
- Monitor pipelines and databases using latency, failures, resource use, and workload metrics.
- Governance and compliance must be considered throughout the data lifecycle.
