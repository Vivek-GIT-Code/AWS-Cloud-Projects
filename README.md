# AWS Projects 

## Project 1 Overview: 
 - The project aims to migrate data from the City of Vancouver to an AWS cloud platform and create a comprehensive data analytics pipeline. The goal is to streamline data processing, analysis, and visualization for various city departments, ensuring scalability, security, and efficiency in data management.

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

### Methodology

Data Analytical Question Formulation
 - Delved into the data for 2023 and 2024 to produce a metric called “Percentage of Calls handled.” The metric will provide the percentage of calls handled in the years 2023 and 2024, respectively
 - Percentage of calls handled = (Number of calls handled/ Number of calls offered) * 100
   
   ![Metrics](https://github.com/VivekCodeCrafter/AWS-Cloud-Project/blob/bd538da4b102a01b9f5fda7b91990f1b4537735d/Images/Picture1.png)

Data Discovery
- Focussed on the procedure ‘Contact Centre Metrics’ in the Government and Finance department for the city of Vancouver.
- Data was sourced from the City of Vancouver website.
- Utilized datasets  in Excel Format is as shown below.
   
   ![Question Formulation](https://github.com/VivekCodeCrafter/AWS-Cloud-Project/blob/959d4aa9e6ea5f4dc622d78a5e7477ad2bf55c2d/Images/Picture2.png)
  
Data Storage Design
 - Utilized Amazon S3 for scalable and secure storage, categorizing data into three stages: Landing, Raw, and Curated.

Dataset Preparation
 - Involved data collection, ETL processes, and data cleaning using AWS Glue DataBrew.

Data Pipeline Design
 - Designed using draw.io to automate data processing stages.

Data Analysis
 - Performed using AWS Athena for querying and deriving insights.
   
### AWS Services
 - AWS Services: Amazon S3 for storage, EC2 for computation, AWS Glue for ETL processes, and Athena for data analysis.
 
### Data Pipeline Implementation:
 - Implemented using AWS Glue for ETL processes.
 - Transformation operations included schema changes, aggregation, and union operations.
   
   ![Data Pipeline](https://github.com/VivekCodeCrafter/AWS-Cloud-Project/blob/e223ff041416c74605764261a210bb18d737121c/Images/Picture3.png)

### Data Analysis
 - Data analysis was performed using AWS Athena.
 - SQL database was utilized to analyze the content of the dataset.
 - Table DDL

```sql
  --Cleaned DIM_DateTable --
CREATE EXTERNAL TABLE `gov_fin_contactcentre_table_vivek`(
  `year` string, 
  `percent_of_calls_handled` string)
ROW FORMAT DELIMITED 
  FIELDS TERMINATED BY ',' 
STORED AS INPUTFORMAT 
  'org.apache.hadoop.mapred.TextInputFormat' 
OUTPUTFORMAT 
  'org.apache.hadoop.hive.ql.io.HiveIgnoreKeyTextOutputFormat'
LOCATION
  's3://project1-gov-fin-vivek-dataset/Government and Finance Domain/Curated/Yearly Analysis'
TBLPROPERTIES (
  'classification'='csv', 
  'skip.header.line.count'='1', 
  'transient_lastDdlTime'='1724308959')
```
   ![Data Anlaysis](https://github.com/VivekCodeCrafter/AWS-Cloud-Project/blob/c7550f7b1494d1871892d5927adda31e96f0fd66/Images/Picture4.png)

### Outcome
 - General Server and Web Server were set up using Amazon EC2 for internal and external data access.
 - Published the annual analysis report on the percentage of calls handled for public access.
   
![Data Publishing](https://github.com/VivekCodeCrafter/AWS-Cloud-Project/blob/752a31569e76695a2524a152ace1461959bddc4c/Images/Picture5.png)

### Conclusion
 - The project showcases the effectiveness of using AWS cloud services for large-scale data analytics and highlights the capabilities in automating data workflows and gaining insights for city management.
