# Project Overview: 
 - Transition of the 'City of Vancouver' portal data to AWS cloud. 
 - Development of a Data Analytics Pipeline (DAP) using AWS services.
 - Focus on scalability, security, and automation in data handling.

## Table of Contents
 - [Data Analytical Question Formulation](#data-analytical-question-formulation)
 - [Data Discovery](#data-discovery)
 - [Data Storage Design](#data-storage-design)
 - [Dataset Preparation](#dataset-preparation)
 - [Data Ingestion](#data-ingestion)
 - [Data Storage](#data-storage)
 - [Data Pipeline Design](#data-pipeline-design)
 - [Data Analysis](#data-analysis)
 - [Data Visualisation](#data-visualisation)
 - [Data Publishing](#data-publishing) 

### Data Analytical Question Formulation
 - I chose to focus on the procedure ‘Contact Centre Metrics’ in the Government and Finance department for the city of Vancouver. 
 - Data was sourced from the City of Vancouver website.
 - Utilized datasets  in Excel Format is as shown below.
   ![Operational Data](https://github.com/VivekCodeCrafter/AWS-Cloud-Project/blob/d616dafead405bcac2530afaa6d3f99090684b99/Images/Picture1.png)
 - I have delved into the data for 2023 and 2024 to produce a metric called “Percentage of Calls handled.” The metric will provide the percentage of calls handled in the years 2023 and 2024, respectively
 - Percentage of calls handled = (Number of calls handled/ Number of calls offered) * 100

### Dataset Preparation
 - Data was collected in Excel format for the years 2023 and 2024.
 - ETL operations were used to prepare the dataset for analysis.

### Data Ingestion
 - Data ingestion was performed using AWS services.
 - Data was uploaded into the S3 bucket using the 'Standard' storage class for frequent access.

### Data Storage
 - S3 general bucket was created for storing data in different folders (Landing, Raw, Curated).
 - Data was categorized based on the year and processing stage.

### Data Pipeline Design
 - A systematic design for the data pipeline was created using draw.io.
 - Steps for metrics calculation like "Percentage of Calls Handled" were defined.

### Data Cleaning
 - AWS Glue Databrew was used to clean the datasets for the years 2023 and 2024.
 - Ensured no missing or invalid values were present in the data.

### Data Structuring
 - The dataset was structured using AWS Glue DataBrew.
 - Columns were renamed, and data types were adjusted to fit the analysis requirements.

### Data Pipeline Implementation:
 - Implemented using AWS Glue for ETL processes.
 - Transformation operations included schema changes, aggregation, and union operations.

### Data Analysis
 - Data analysis was performed using AWS Athena.
 - SQL database was utilized to analyze the content of the dataset.

### Data Visualization:
 - AWS Quicksight was intended for data visualization but was not available, so Excel was used instead.
Visualizations were created to showcase the analysis findings.

### Data Publishing
 - General Server and Web Server were set up using Amazon EC2 for internal and external data access.
Published the annual analysis report on the percentage of calls handled for public access.
