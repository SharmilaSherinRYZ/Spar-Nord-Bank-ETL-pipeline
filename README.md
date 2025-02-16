# Data-Driven ATM Performance Analytics
This project analyzes ATM transaction data for Spar Nord Bank to improve refill planning and operational efficiency. Using AWS and Spark, it extracts transaction details from MySQL, processes the data, and stores it in Redshift for analysis. This helps identify transaction trends, ATM failures, and other key insights.

# Architecture

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/SharmilaSherinRYZ/Spar-Nord-Bank-ETL-pipeline/refs/heads/main/sparknodETL1.drawio.png">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/SharmilaSherinRYZ/Spar-Nord-Bank-ETL-pipeline/refs/heads/main/sparknodETL1.drawio.png">
  <img alt="Spotify Pipeline Architecture" src="https://raw.githubusercontent.com/SharmilaSherinRYZ/Spar-Nord-Bank-ETL-pipeline/refs/heads/main/sparknodETL1.drawio.png">
</picture>

# Dataset Information
The dataset used in this project is stored in Amazon RDS, a managed relational database service by AWS. The database credentials required for access are provided by our organization and are not included in this repository for security reasons.

# Services Used

Amazon RDS – A managed relational database service that stores structured data and supports various database engines like MySQL, PostgreSQL, and SQL Server.

Apache Sqoop – A tool designed to transfer bulk data between relational databases (like Amazon RDS) and Hadoop-based storage systems like HDFS.

Hadoop HDFS – A distributed file system that enables scalable storage and processing of large datasets across multiple nodes.

Apache PySpark – The Python API for Apache Spark, used for distributed data processing, transformation, and analysis.

Amazon S3 – A highly scalable object storage service used for storing transformed data before loading it into the data warehouse.

Amazon Redshift – A cloud data warehouse optimized for analytics, allowing efficient querying of large datasets.

# Project Execution Flow

Extract Data from Amazon RDS → Use Apache Sqoop to transfer structured data from Amazon RDS to HDFS for further processing.

Transform Data Using PySpark → Load the extracted data into HDFS, clean, process, and transform it using PySpark.

Load Transformed Data into Amazon S3 → Store the processed data in Amazon S3 for staging before loading into the data warehouse.

Load Data into Amazon Redshift → Use the COPY command to efficiently transfer data from Amazon S3 into Amazon Redshift.

Perform Data Analysis → Query and analyze the loaded data in Redshift using BI tools for reporting and insights.
