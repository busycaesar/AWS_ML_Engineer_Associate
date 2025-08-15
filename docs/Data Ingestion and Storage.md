---
sidebar_position: 2
---
## Types of Data
- Structured
- Unstructured and
- Semi-structured
## Properties of Data (Three Vs)
### Volume
- Amount and Size
- Gigabytes to Petabytes
- Challenges in storing, processing and analyzing
### Velocity
- Speed at which the new data is generated, collected and processed.
- High speed requires real-time or near to real-time data processing capabilities.
### Variety
- [Type](Data%20Ingestion%20and%20Storage.md#Types%20of%20Data) and source of data.
- Data can be collected from multiple sources and in various types.
## Data Warehouse
- A centralized repository where data from different sources is stored in a structured format.
### Characteristics
- Complex queries and analysis
- [ETL Pipelines](Data%20Ingestion%20and%20Storage.md#ETL%20Pipelines)
- Uses Star/Snowflake schema
- Optimized for read-heavy operations
### Tool
-   [Amazon Redshift](AWS%20Tools.md#Amazon%20Redshift)

![Data Warehouse](data-warehouse.png)

## Data Lake
- A repository that stores large amount of raw data in its original [type](Data%20Ingestion%20and%20Storage.md#Types%20of%20Data).
### Characteristics
- Store large volumes of raw data without predefined schema or preprocessing.
- Supports batch, real-time and stream processing.
### Tools
- [Amazon S3](AWS%20Tools.md#Amazon%20S3)
- [AWS Glue](AWS%20Tools.md#AWS%20Glue)
- [Amazon Athena](AWS%20Tools.md#Amazon%20Athena)
## Data Warehouse VS Data Lake

| [Data Warehouse](Data%20Ingestion%20and%20Storage.md#Data%20Warehouse)               | [Data Warehouse](Data%20Ingestion%20and%20Storage.md#Data%20Warehouse)                   |
| ------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------- |
| Schema-on-write (predefined before writing data)<br>Extract - Transform - Load (ETL) | Schema-on-read (defined at the time of reading data)<br>Extract - Load - Transform (ELT) |
| Less agile due to predefined schema                                                  | More agile as it stores raw data without a predefined schema.                            |
| More expensive because of optimizations of complex queries                           | Cost-effective storage solutions, but it can rise when processing large amounts of data  |
### Use Data Warehouse when
- Structured data sources and require fast and complex queries
- Business intelligence and analytics are primary use cases.
### Use Data Lake when
- Mix [type of data](Types%20of%20Data.md#Types%20of%20Data).
- Need scalable and cost-effective solution to store massive amounts of data.
- Future needs for data are uncertain; hence need flexibility in storage and processing.
- Advanced analytics, machine learning and data discovery are goals.
## Data Lakehouse
- Provide performance, reliability and capability of [Data Warehouse](Data%20Ingestion%20and%20Storage.md#Data%20Warehouse)
- Maintaining the flexibility, scale and low-cost storage of [Data Lake](Data%20Ingestion%20and%20Storage.md#Data%20Lake).
### Characteristics
- Supports both types of data.
- Allows for schema-on-write and schema-on-read.
- Capabilities for both detailed analytics and machine learning tasks.
### Tool
[AWS Lake Formation](AWS%20Tools.md#AWS%20Lake%20Formation)
## ETL Pipelines
- Extract, Transform, Load
- Process to move data from source systems into a data warehouse.
### Extract
- Retrieve raw data from sources like database, CRMs, files, APIs etc.
- Ensuring data integrity (data is not missing or corrupting).
- Real-time or batches
### Transform
- Convert data into suitable format.
- Can include the following operations:
	- Data Cleansing (removing duplicates, fixing errors)
	- Data Enrichment (adding data from other sources)
	- Format Changes (date formatting, etc.)
	- Aggregations or computations (calculating totals or averages)
	- Encoding/Decoding data
	- Handling missing values
### Load
- Move the transformed data into data warehouse or another data repository.
- Can be done in batches or as streaming.
- Ensuring data integrity.
### Managing ETL Pipelines
- Process must be automated.
- [AWS Glue](AWS%20Tools.md#AWS%20Glue)
## Data Sources
- JDBC
	- Java DB Connectivity
	- Platform independent
	- Language dependent
- ODBC
	- Open DB Connectivity
	- Platform dependent
	- Language independent
- Raw Logs
- APIs
- Streams
## Common Data Formats
### CSV (Comma-Separated Values)
- Text based format where each line is a row and values in a row are separated by a delimiter.
#### When to use?
- Small to medium datasets
- Data interchange between systems with different technology
- Human readable and editable data storage
- Importing/Exporting data from databases/spreadsheets
#### Systems
- Databases (SQL-based), Excel, Pandas (Python), R, etc.
### JSON (JavaScript Object Notation)
- Lightweight, text-based and human readable data interchange format.
- Structured or semi-structured data based on key-value pairs.
#### When to use?
- Data interchange between web server and web client.
- Config and settings for applications.
- Need flexible schema or nested data structures.
#### Systems
- Web browsers, JavaScript, Python, Java, Restful APIs, NoSQL
### Avro
- Binary format that stores both the data and its schema, allowing it to be processed later.
#### When to use?
- Big data and real-time processing systems.
- When changes in data structure is needed.
- Efficient serialization for data transport between systems.
#### Systems
- Apache Kafka, Apache Spark, Apache Flink, Hadoop Ecosystem.
### Parquet
- Columnar storage format, optimized for analytics.
- Efficient compression and encoding schemes.
#### When to use?
- Analyzing large datasets with analytics engines.
- Reading specific column instead of entire record is beneficial.
- Storing data on distributed systems where I/O operations and storage needs optimization.
#### Systems
- Hadoop ecosystem, Apache Spark, Apache Hive, Apache Impala, Amazon Redshift Spectrum.
## [Amazon S3](Amazon%20S3.md)
## [EBS Volume](EBS%20Volume.md)
## [Amazon EFS](Amazon%20EFS.md)
## EBS Volume VS Amazon EFS
### EBS Volume
- One Instance (Except multi-attach I/O)
- Locked at Availability Zone level
- To migrate, take a snapshot and restore the snapshot in another AZ.
- Root EBS Volumes of instances get terminated by default if the EC2 instance gets terminalted. (It can be disabled.)
### Amazon EFS
- Mounting 100s of instances across AZ.
- Only for Linux Instances (POSIX)
- Higher price than EBS but can leverage Storage Tiers for cost savings.
## Amazon FSx
### Overview
- Launching 3rd party high-performance file systems on AWS.
### FSx For Lustre
- Parallel distributed file system for large scale computing.
- Lustre = Linux + Cluster
- Seemless integration with S3
	- Can read S3 as a file system.
## [Amazon Kinesis Data Streams](Amazon%20Kinesis%20Data%20Streams.md)
## [Amazon Data Firehose](Amazon%20Data%20Firehose.md)
## Kinesis Data Streams VS Amazon Data Firehose

| [Kinesis Data Streams](Amazon%20Kinesis%20Data%20Streams.md)                                                                                | [Amazon Data Firehose](Amazon%20Data%20Firehose.md)                           |
| ------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Streaming data collection                                                                                                                   | Load streaming data into S3 / Redshift / OpenSearch / 3rd party / custom HTTP |
| Producer and Consumer Code                                                                                                                  | Fully Managed                                                                 |
| Real-Time                                                                                                                                   | Near Real-Time                                                                |
| [Provisioned](Amazon%20Kinesis%20Data%20Streams.md#Provisioned%20Mode) / [On-Demand](Amazon%20Kinesis%20Data%20Streams.md#On-demand%20Mode) | Automatic Scaling                                                             |
| Data Storage upto 365 days                                                                                                                  | No data storage                                                               |
| Reply capability                                                                                                                            | Does not support reply capability                                             |
## ss