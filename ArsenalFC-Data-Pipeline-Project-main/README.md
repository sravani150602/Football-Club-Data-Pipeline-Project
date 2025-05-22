# Arsenal FC Data Pipeline Project

This project demonstrates an end-to-end data engineering pipeline built to collect, process, store, and visualize football statistics related to Arsenal Football Club from 2017 to 2023.

## Overview

- Extracts raw data from CSV files
- Transforms and loads data into PostgreSQL using Python and Apache Spark
- Schedules ETL jobs using Apache Airflow
- Visualizes insights using Power BI dashboards

## Tools Used

- Python
- Apache Spark
- PostgreSQL
- Apache Airflow
- Docker
- Power BI
- Jupyter Notebooks

## Project Structure

1. Data Ingestion from CSVs
2. Data Cleaning and Transformation with Spark
3. Loading into PostgreSQL with a Galaxy Schema
4. Automation via Airflow DAGs
5. Visualization using Power BI

## Setup

- Clone this repo
- Navigate to `Docker_files` and run:

```bash
docker-compose up -d
