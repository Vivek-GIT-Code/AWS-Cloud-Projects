# AWS Projects 

## Project 1 Objective: 
 - The project aims to migrate data from the City of Vancouver to an AWS cloud platform and create a comprehensive data analytics pipeline. The goal is to streamline data processing, analysis, and visualization for various city departments, ensuring scalability, security, and efficiency in data management.

## Table of Contents
 - [Methodology](#methodology)
 - [Data Discovery](#AWS-Services)
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
- Utilized datasets  in Excel Format is as shown below.
   
   ![Question Formulation](https://github.com/VivekCodeCrafter/AWS-Cloud-Project/blob/959d4aa9e6ea5f4dc622d78a5e7477ad2bf55c2d/Images/Picture2.png)
  
Data Storage Design
 - Utilized Amazon S3 for scalable and secure storage, categorizing data into three stages: Landing, Raw, and Curated.

Dataset Preparation
 - Involved: 
 - Data collection
 - ETL processes
 - Data cleaning using AWS Glue DataBrew.

Data Pipeline Design
 - Designed using draw.io to automate data processing stages.

Data Analysis
 - Performed using AWS Athena for querying and deriving insights.
   
### AWS Services
 - AWS Services:
 - Amazon S3 for storage
 - EC2 for computation
 - AWS Glue for ETL processes
 - Athena for data analysis.
 
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

### Insights and Findings
 - 2023: The percentage of calls handled was 94.19%, indicating a high efficiency in managing calls at the '3-1-1 contact center' for the City of Vancouver during this year.
 - 2024: The percentage of calls handled dropped slightly to 92.93%. This reduction, although minor, indicates a slight decline in the call-handling efficiency compared to the previous year.
 - Comparison: There is a noticeable decrease of approximately 1.26% in the percentage of calls handled from 2023 to 2024. This could be due to various factors such as an increase in call volume, changes in operational procedures, or resource allocation challenges.

### Cost Estimation
 - Amazon S3: Estimated annual expense of $285.846 for storage across four buckets.
 - AWS Glue DataBrew: Estimated yearly cost of $32.04 for cleaning and restructuring datasets.
 - AWS Glue: Estimated total cost of $13.20 for ETL job runs.
 - Amazon Athena: Estimated annual expense of $35.76 for querying and analysis.
 - EC2: Total yearly cost of $225.96 for hosting general and web servers.

### Conclusion
 - The project showcases the effectiveness of using AWS cloud services for large-scale data analytics and highlights the capabilities in automating data workflows and gaining insights for city management.
