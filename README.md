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
   ![Question Formulation](https://github.com/VivekCodeCrafter/AWS-Cloud-Project/blob/959d4aa9e6ea5f4dc622d78a5e7477ad2bf55c2d/Images/Picture2.png)
 - I have delved into the data for 2023 and 2024 to produce a metric called “Percentage of Calls handled.” The metric will provide the percentage of calls handled in the years 2023 and 2024, respectively
 - Percentage of calls handled = (Number of calls handled/ Number of calls offered) * 100
   ![Metrics](https://github.com/VivekCodeCrafter/AWS-Cloud-Project/blob/bd538da4b102a01b9f5fda7b91990f1b4537735d/Images/Picture1.png)

### Data Pipeline Design
 - A systematic design for the data pipeline was created using draw.io.
 - Steps for metrics calculation like "Percentage of Calls Handled" were defined.

### Data Cleaning and Structuring
 - AWS Glue Databrew was used to clean the datasets for the years 2023 and 2024.
 - Ensured no missing or invalid values were present in the data.
 - The dataset was structured using AWS Glue DataBrew.
 - Columns were renamed, and data types were adjusted to fit the analysis requirements.

### Data Pipeline Implementation:
 - Implemented using AWS Glue for ETL processes.
 - Transformation operations included schema changes, aggregation, and union operations.
   ![Data Pipeline](https://github.com/VivekCodeCrafter/AWS-Cloud-Project/blob/e223ff041416c74605764261a210bb18d737121c/Images/Picture3.png)

### Data Analysis
 - Data analysis was performed using AWS Athena.
 - SQL database was utilized to analyze the content of the dataset.
   ![Data Anlaysis](https://github.com/VivekCodeCrafter/AWS-Cloud-Project/blob/272761fc38ffc35709d3e60874ea308f7b949cfc/Images/Picture4.png)

### Data Publishing
 - General Server and Web Server were set up using Amazon EC2 for internal and external data access.
Published the annual analysis report on the percentage of calls handled for public access.
