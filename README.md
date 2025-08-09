# Arsenal FC Data Pipeline & Analysis Project

A comprehensive data engineering pipeline built to process and analyze Arsenal Football Club’s player, goalkeeper, and match data spanning the 2017–2023 seasons. This project extracts raw data, transforms and loads it into a data warehouse, and provides insightful visualizations for performance analysis.

---

## Table of Contents
- [Project Overview](#project-overview)  
- [Tech Stack & Architecture](#tech-stack--architecture)  
- [Pipeline Workflow](#pipeline-workflow)  
- [Getting Started](#getting-started)  
- [Data Model](#data-model)  
- [Visualization & Insights](#visualization--insights)  
- [Contributing](#contributing)  
- [License](#license)  

---

## Project Overview

This project implements an end-to-end data pipeline that:

- Ingests raw data from CSV files related to Arsenal FC’s matches, players, and goalkeepers.
- Uses Apache Spark for distributed data processing and transformation.
- Loads processed data into a PostgreSQL data warehouse.
- Orchestrates the ETL workflow with Apache Airflow.
- Provides visual insights via PowerBI dashboards and Jupyter notebooks.

---

## Tech Stack & Architecture

| Layer             | Technology / Tool         | Purpose                                         |
|-------------------|--------------------------|------------------------------------------------|
| **Ingestion**     | Apache Spark (PySpark)   | Reading raw CSV data, distributed data processing |
| **Storage**       | PostgreSQL               | Central relational database & data warehouse   |
| **Orchestration** | Apache Airflow           | Scheduling and monitoring ETL workflows        |
| **ETL Scripting** | Python & Jupyter Notebooks | Transformation & pipeline logic implementation  |
| **Serving Layer** | PowerBI                  | Interactive data visualization & dashboards    |
| **Infrastructure**| Docker & Docker Compose  | Containerized environment for consistent deployment |

---

## Pipeline Workflow

### 1. Data Ingestion
- Raw data (CSV files) for matches, players, and goalkeepers are read using Apache Spark.
- Spark’s distributed processing enables efficient handling of large datasets.
- Data is loaded into raw staging tables in PostgreSQL using JDBC.

### 2. Data Transformation
- Data cleaning, formatting, and normalization are performed using Spark SQL and DataFrame APIs.
- Derived columns such as unique match identifiers and formatted dates are created.
- Duplicates and missing values are handled.

### 3. Data Loading to Data Warehouse
- Transformed data is loaded into a PostgreSQL schema optimized for analytics (`dwh` schema).
- Implements a **Galaxy Schema** with separate fact tables for players and goalkeepers, and dimension tables for matches, dates, and player attributes.

### 4. Orchestration
- Apache Airflow DAG (`etl_arsenalfc`) automates running of ETL tasks in the correct sequence.
- Provides monitoring, logging, and scheduling capabilities.

### 5. Serving & Visualization
- Data is accessed from PostgreSQL via PowerBI.
- Eight custom dashboards provide deep insights on player and match performances.
- Jupyter notebooks provide flexible ad-hoc analysis using PySpark.
