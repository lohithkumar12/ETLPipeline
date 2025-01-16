# ETL Pipeline with Airflow and PostgreSQL

[![Docker](https://img.shields.io/badge/Docker-Enabled-blue)](https://www.docker.com/)  
[![Airflow](https://img.shields.io/badge/Airflow-2.5.0-green)](https://airflow.apache.org/)  
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-AWS_RDS-blue)](https://aws.amazon.com/rds/)  
[![Astronomer](https://img.shields.io/badge/Astronomer-Cloud-orange)](https://www.astronomer.io/)

---

## Table of Contents
- [Project Overview](#project-overview)
- [Key Components](#key-components)
- [Objectives](#objectives)
- [Architecture and Workflow](#architecture-and-workflow)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Deployment](#deployment)
- [Contributing](#contributing)

---

## Project Overview
This project demonstrates an **ETL pipeline** orchestrated using **Apache Airflow** to extract data from NASA's Astronomy Picture of the Day (APOD) API, transform it, and load it into a **PostgreSQL database** hosted on **AWS RDS**. The orchestration and workflow management are hosted on **Astronomer Cloud**, ensuring scalability and reliability. Data visualization and management are achieved using **DBeaver**.

---

## Key Components
1. **Airflow for Orchestration**:
   - Schedules, monitors, and executes the ETL pipeline using Directed Acyclic Graphs (DAGs).
2. **PostgreSQL on AWS RDS**:
   - Stores transformed data in a highly available and scalable cloud database.
3. **NASA API**:
   - Provides daily astronomy-related data, including titles, explanations, and image URLs.
4. **DBeaver**:
   - Used for querying and visualizing data in the PostgreSQL database.

---

## Objectives
1. **Extract Data**:
   - Fetch JSON data from NASA's API using `SimpleHttpOperator`.
2. **Transform Data**:
   - Process API data, clean fields, and prepare it for database storage.
3. **Load Data**:
   - Insert the processed data into PostgreSQL tables using Airflow's `PostgresOperator`.

---

## Architecture and Workflow
1. **Extract**:
   - Data is fetched from NASA's API using `SimpleHttpOperator`.
2. **Transform**:
   - Fields such as `title`, `explanation`, and `url` are cleaned and structured.
3. **Load**:
   - The transformed data is stored in a PostgreSQL database hosted on AWS RDS.

---

## Setup Instructions

### **Local Setup**
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/lohithkumar12/ETLPipeline.git
   cd ETLPipeline
   ```

2. **Install Prerequisites**:
   - **Docker**: Install Docker and Docker Desktop.
   - **Astronomer CLI**: Follow the [Astronomer CLI installation guide](https://docs.astronomer.io/astro/cli).

3. **Start Docker Services**:
   - Launch Airflow and PostgreSQL using Docker Compose:
     ```bash
     docker-compose up
     ```

4. **Access the Airflow UI**:
   - Navigate to `http://localhost:8080` in your browser.
   - Login credentials:
     - **Username**: `airflow`
     - **Password**: `airflow`.

---

## Usage
1. **Trigger the DAG**:
   - Open the Airflow UI and trigger the DAG named `etl_pipeline`.

2. **Monitor Workflow**:
   - Track task dependencies, execution status, and logs in the Airflow UI.

3. **Connect to PostgreSQL**:
   - Use **DBeaver** or any database client to query the database:
     - **Host**: AWS RDS Endpoint
     - **Port**: `5432`
     - **Username**: `postgres`
     - **Password**: `your-password`
     - **Database**: `postgres`.

---

## Deployment
1. **Orchestration on Astronomer Cloud**:
   - DAGs are hosted on **Astronomer Cloud** for reliable and scalable workflow execution.
2. **Database on AWS RDS**:
   - The PostgreSQL database is deployed on AWS RDS for managed and fault-tolerant database services.
3. **Data Visualization**:
   - Connect to AWS RDS using **DBeaver** to visualize and inspect data.

---

## Contributing
Contributions are welcome! Here's how you can contribute:
1. Fork the repository.
2. Create a new feature branch.
3. Submit a pull request.


