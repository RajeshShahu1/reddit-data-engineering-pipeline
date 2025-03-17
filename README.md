# Reddit Data Engineering Pipeline using Reddit, Airflow, Celery, Postgres, S3, AWS Glue, Athena, and Redshift

This project delivers a complete data pipeline solution for extracting, transforming, and loading (ETL) Reddit data into a Redshift data warehouse. It utilizes a range of tools and services such as Apache Airflow, Celery, PostgreSQL, Amazon S3, AWS Glue, Amazon Athena, and Amazon Redshift.
## Contents

- [Project Overview](#project-overview)
- [Architecture](#architecture)
- [Setup Prerequisites](#setup-prerequisites)
- [Installation Guide](#installation-guide)
- [Running the Pipeline](#running-the-pipeline)

## Project Overview

The goal of this pipeline is to:

1. Extract data from Reddit's API.
2. Store raw JSON data in an Amazon S3 bucket.
3. Transform and catalog the data using AWS Glue.
4. Query and refine the data with Amazon Athena.
5. Load the structured data into Amazon Redshift for analysis.
6. Automate the entire process using Apache Airflow with Celery workers.

## Architecture
![RedditDataEngineering.png](RedditDataEngineering.png)

The project leverages the following tools and services:

- **Reddit API** – Retrieves raw data.
- **Apache Airflow** – Manages and orchestrates tasks.
- **Celery** – Distributes workloads across multiple workers.
- **PostgreSQL** – Stores metadata and intermediate results.
- **Amazon S3** – Stores extracted raw data.
- **AWS Glue** – Handles data transformation and cataloging.
- **Amazon Athena** – Enables SQL-based querying.
- **Amazon Redshift** – Stores processed data for analytics.

## Setup Prerequisites

Before proceeding with installation, ensure you have:

- A valid AWS account with necessary permissions.
- Reddit API credentials for data extraction.
- Docker installed for containerized execution.
- Python 3.9+ installed.

## Installation Guide

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/RajeshShahu1/reddit-data-engineering-pipeline.git
   cd reddit-data-engineering-pipeline
   ```
2. **Set Up a Virtual Environment:**
   ```bash
   python3 -m venv env
   source env/bin/activate
   ```
3. **Install Required Packages:**
   ```bash
   pip install -r requirements.txt
   ```
4. **Configure the Project:**
   Rename the configuration file and update credentials:
   ```bash
   mv config.conf.example config.conf
   ```
5. **Launch Services Using Docker:**
   ```bash
   docker-compose up -d
   ```

## Running the Pipeline

Once the setup is complete, you can trigger the pipeline via Airflow's UI or CLI. This will execute the ETL workflow, from data extraction to final storage in Redshift.

For further customization, you can modify DAG configurations inside the `dags/` directory to adjust the scheduling and task dependencies.

This pipeline is designed to be scalable and can be integrated with additional cloud-based tools for further enhancements.

