# Data Workflow with Reddit, Airflow, AWS Glue, AWS Athena, AWS S3, and AWS Redshift, Celery, Postgres

This project outlines a robust solution to extract, process, and store Reddit data in a cloud-based data warehouse. It utilizes a mix of orchestration tools, cloud storage, and analytic services including: Airflow, AWS Glue, AWS Athena, AWS S3, and AWS Redshift, Celery, Postgres
## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Prerequisites](#prerequisites)
- [System Setup](#system-setup)
- [Video](#video)

## Overview

The pipeline is designed to:

1. Extract data from Reddit using its API.
2. Store the raw data into an S3 bucket from Airflow.
3. Transform the data using AWS Glue and Amazon Athena.
4. Load the transformed data into Amazon Redshift for analytics and querying.

The workflow:

1. Retrieves data from Reddit via its API.
2. Saves raw information to cloud storage (S3) using Airflow.
3. Processes and formats data using serverless tools and query engines (AWS Glue and Amazon Athena).
4. Stores the transformed data in a structured database for further analysis (Amazon Redshift).

## Architecture
![RedditDataEngineering.png](assets%2FRedditDataEngineering.png)
1. **Data Source**: Reddit API.
2. **Apache Airflow & Celery**: Orchestrates the ETL process and manages task distribution.
3. **PostgreSQL**: Temporary storage and metadata management.
4. **Amazon S3**: Raw data storage.
5. **AWS Glue**: Data cataloging and ETL jobs.
6. **Amazon Athena**: SQL-based data transformation.
7. **Amazon Redshift**: Data warehousing and analytics.

## Requirements
- AWS Account with appropriate permissions for S3, Glue, Athena, and Redshift.
- Reddit API credentials.
- Docker Installation
- Python 3.9 or higher

## System Setup
1. Clone the repository.
   ```bash
    git clone https://github.com/airscholar/RedditDataEngineering.git
   ```
2. Create a virtual environment.
   ```bash
    python3 -m venv venv
   ```
3. Activate the virtual environment.
   ```bash
    source venv/bin/activate
   ```
4. Install the dependencies.
   ```bash
    pip install -r requirements.txt
   ```
5. Rename the configuration file and the credentials to the file.
   ```bash
    mv config/config.conf.example config/config.conf
   ```
6. Starting the containers
   ```bash
    docker-compose up -d
   ```
7. Launch the Airflow web UI.
   ```bash
    open http://localhost:8080
   ```
