# Uber Data Engineering Project: Google BigQuery and Looker

## Project Overview
This project is an end-to-end data engineering solution designed to analyze Uber's dataset using Google Cloud Platform (GCP) and modern data tools. It incorporates data ingestion, transformation, and visualization to produce valuable insights into Uber trip records. The project leverages GCP services, Google BigQuery for data warehousing, and Looker Studio for data visualization.

## Project Workflow and Steps

### 1. Project Setup
- **Create GCP Storage Bucket**: Create a Google Cloud Storage bucket to store project files, data, and any temporary resources required during data processing.
- **Set Up Compute Instance**: Create a Compute Engine instance in GCP.
  - *Specifications*: 
    - Machine Type: e2-standard-16
    - CPU: 8-core
    - RAM: 64 GB
  - Establish an SSH connection to the instance to allow remote command execution.
- **Install Dependencies on Compute Instance**: Execute commands from the `command.txt` file in the repository. This includes installing:
  - Python 3
  - pandas (data manipulation)
  - maze.ai (data pipeline management)
  - Google Cloud SDK (interacting with GCP services)

### 2. Launch Maze.ai Project
- Start a Maze.ai project to manage and configure data pipelines.
- Run the project on port 6789, accessible through the external IP address of the GCP compute instance.

### 3. Update Firewall Rules
- Update GCP firewall rules to allow external access on port 6789 to view the Maze.ai dashboard.

### 4. Set Up Data Pipelines
- **Create Data Loader Pipeline**: Develop a data ingestion pipeline in Maze.ai to import Uber dataset records.
- **Build Data Transformation Pipeline**: Clean, filter, and process the Uber data to prepare it for analysis by refining formats, removing inconsistencies, and aggregating metrics.
- **Connect to DataExporter for BigQuery**: Export the transformed data to Google BigQuery.

### 5. Configure io_config.yaml for Secure GCP Access
- Create a new service account in GCP with permissions for BigQuery and Storage access.
- Download the service account key and update `io_config.yaml` with the key details for secure access.

### 6. Complete Data Loader Pipeline in BigQuery
- Verify successful data ingestion and transformation by refreshing the dataset in BigQuery Console and previewing the data.

### 7. Data Visualization with Looker Studio
- Use Looker Studio to connect to BigQuery and visualize the Uber dataset.
- Create dashboards to explore metrics such as trip duration, pickup and drop-off locations, fare details, and distances.


## Project Architecture
- **Data Ingestion**: Using Google Storage for staging data and importing into GCP.
- **Data Transformation**: Maze.ai pipelines for transforming raw data.
- **Data Export and Storage**: BigQuery as the data warehouse for analysis-ready data.
- **Visualization**: Looker Studio for creating insightful dashboards based on BigQuery data.

<img width="1258" alt="Project Architecture" src="Graphical Representations/Project Architecture.jpg">

## Data Modeling

<img width="1258" alt="Data Modeling" src="Graphical Representations/Data Modeling.png">

## ETL Pipeline

<img width="1258" alt="Looker Dashbaord" src="Graphical Representations/Looker Dashboard.png">

## Looker Dashboard

<img width="1258" alt="Mage Data Pipeline" src="Graphical Representations/Mage Data Pipeline.png">

## Technology Stack
- **Languages**:
  - Python (for data manipulation and pipeline scripting)
  - SQL (for data querying in BigQuery)

- **Google Cloud Platform**:
  - Google Storage: Data storage and staging
  - Compute Engine: Running pipelines and data processing
  - BigQuery: Data warehousing for analytics
  - Looker Studio: Visualization and dashboarding

- **Modern Data Pipeline Tool**:
  - Mage.ai: Used for building data ingestion, transformation, and export pipelines.

## Data Source
The dataset used is the TLC Trip Record Data provided by New York City's Taxi and Limousine Commission, which includes:
- **Dates/Times**: Pickup and drop-off timestamps
- **Locations**: Pickup and drop-off zones
- **Trip Details**: Distance, fare components, rate types, payment methods, and passenger counts

Data source link: https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

Data Dictionary: https://www.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf

## Project Dependencies
To run this project, ensure the following dependencies are installed:
- Python 3
- pandas
- maze.ai
- Google Cloud SDK
- Google BigQuery client library

## Conclusion
This Uber Data Engineering Project demonstrates the power and flexibility of using Google Cloud Platform services to build scalable and efficient data pipelines. By leveraging Google BigQuery for data storage and analytics and Looker Studio for visualization, we have created an end-to-end solution that processes large datasets, transforms them for analysis, and delivers insights through dynamic dashboards.

**Key takeaways**:
- **Effective Data Management**: GCP storage and BigQuery enable efficient handling and querying of large datasets.
- **Pipeline Automation with Mage.ai**: Simplifies the setup of robust ETL pipelines for smooth data ingestion, transformation, and export processes.
- **Insightful Visualization with Looker Studio**: Allows easy exploration of trip data patterns, fare trends, and regional trip behavior.

This project provides a foundation for analyzing transportation data and serves as a framework for implementing similar data engineering solutions across various industries. It showcases a scalable approach to data-driven decision-making in the digital age.
