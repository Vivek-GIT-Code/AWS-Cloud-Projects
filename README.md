# Project 1 Objective
 - The project aims to migrate data from the City of Vancouver to an AWS cloud platform and create a comprehensive data analytics pipeline. The goal is to streamline data processing, analysis, and visualization for various city departments, ensuring scalability, security, and efficiency in data management.

## Table of Contents
 - [Methodology](#methodology)
 - [Data Discovery](#AWS-Services)
 - [Data Pipeline Design](#data-pipeline-design)
 - [Data Analysis](#data-analysis)
 - [Data Visualisation](#data-visualisation)
 - [Data Publishing](#data-publishing)

## Methodology

### Data Analytical Question Formulation
 - Delved into the data for 2023 and 2024 to produce a metric called “Percentage of Calls handled.” The metric will provide the percentage of calls handled in the years 2023 and 2024, respectively
 - Percentage of calls handled = (Number of calls handled/ Number of calls offered) * 100
   
   ![Metrics](https://github.com/user-attachments/assets/b4ba5957-631f-40cb-843f-3cbc6c1e20c9)

### Data Discovery
- Focussed on the procedure ‘Contact Centre Metrics’ in the Government and Finance department for the city of Vancouver.
- Utilized datasets  in Excel Format is as shown below.
   
   ![Question Formulation](https://github.com/user-attachments/assets/83f35f73-b08c-4036-9ee7-a5299c6434ee)
  
### Data Storage Design
 - Utilized Amazon S3 for scalable and secure storage, categorizing data into three stages: Landing, Raw, and Curated.

### Dataset Preparation
 - Involved:
    - Data collection
    - ETL processes
    - Data cleaning using AWS Glue DataBrew.

### Data Pipeline Design
 - Designed using draw.io to automate data processing stages.

![Pipeline](https://github.com/user-attachments/assets/1db2d1a2-0146-4cdc-8ca0-635b5c38f8c3)

### Data Analysis
 - Performed using AWS Athena for querying and deriving insights.
   
## AWS Services
 - AWS Services:
    - Amazon S3 for storage
    - EC2 for computation
    - AWS Glue for ETL processes
    - Athena for data analysis.
 
## Data Pipeline Implementation:
 - Implemented using AWS Glue for ETL processes.
 - Transformation operations included schema changes, aggregation, and union operations.
    - Change Schema Operation: The schema of the 2023 and 2024 dataset has been changed by deleting all other columns that are not required and keeping and renaming the columns BI_ID, Year, calls_offered, and calls_handled.
    - Aggregate Operation: The aggregate function has been used to aggregate the records of the ‘Year’ column within the 2023 and 2024 dataset.
    - Union Operation: In order to prepare a collective dataset out of 2023 and 2024 records, the Union function has been utilized to create a new output from all the records of the two similar input datasets.
    - Change Schema: At this stage, unwanted columns have been deleted by using the change schema operation
    - Derived Column: At this stage, the matric is calculated by performing the SQL operation
Calls handled Percentage = (calls_handled/calls_offered) *100.
   
   ![Data Pipeline](https://github.com/user-attachments/assets/3e9b389a-6083-4f76-97de-90bf7b0b63e2)

## Data Analysis
 - Data analysis was performed using AWS Athena.
 - SQL database was utilized to analyze the content of the dataset.
 - Table DDL

```sql
  --Contact Centre Table --
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
 - Data as pulled from AWS Athena Database is as shown below:
   
![Data Anlaysis](https://github.com/user-attachments/assets/c214f109-7a25-4891-930e-68468c60c921)

## Outcome
 - General Server and Web Server were set up using Amazon EC2 for internal and external data access.
 - Published the annual analysis report on the percentage of calls handled for public access.
   
![Data Publishing](https://github.com/user-attachments/assets/77a924dd-3efb-46c8-aef0-2a18660fa08f)

## Insights and Findings
 - 2023: The percentage of calls handled was 94.19%, indicating a high efficiency in managing calls at the '3-1-1 contact center' for the City of Vancouver during this year.
 - 2024: The percentage of calls handled dropped slightly to 92.93%. This reduction, although minor, indicates a slight decline in the call-handling efficiency compared to the previous year.
 - Comparison: There is a noticeable decrease of approximately 1.26% in the percentage of calls handled from 2023 to 2024. This could be due to various factors such as an increase in call volume, changes in operational procedures, or resource allocation challenges.

## Cost Estimation
 - Amazon S3: Estimated annual expense of $285.846 for storage across four buckets.
 - AWS Glue DataBrew: Estimated yearly cost of $32.04 for cleaning and restructuring datasets.
 - AWS Glue: Estimated total cost of $13.20 for ETL job runs.
 - Amazon Athena: Estimated annual expense of $35.76 for querying and analysis.
 - EC2: Total yearly cost of $225.96 for hosting general and web servers.

## Conclusion
 - The project showcases the effectiveness of using AWS cloud services for large-scale data analytics and highlights the capabilities in automating data workflows and gaining insights for city management.

# Project 2 Objective
 - The objective of this project is to accurately calculate the student graduation rates for the years 2022, 2023 and 2024 at the University Canada West (UCW).
 - By leveraging sample data, such as student records and course completion information, this project seeks to uncover key insights into student performance, identify trends, and offer data-driven recommendations to improve future graduation rates.

## Table of Contents
 - [Methodology](#methodology)
 - [Data Discovery](#AWS-Services)
 - [Data Pipeline Design](#data-pipeline-design)
 - [Data Analysis](#data-analysis)
 - [Data Visualisation](#data-visualisation)
 - [Data Publishing](#data-publishing)

### Data Analytical Question Formulation
 - Delved into the sample data for 2022, 2023 and 2024 to produce a metric called “Student Graduation Rate.” The metric will provide the percentage of student graduated in the years 2022, 2023 and 2024, respectively.
 - Percentage of Students Graduated (SGR) = (Number of Student Enrolled/ Number of Student Graduated) * 100
  
### Dataset Preparation
 - Sample dataset includes two Excel files
    - Sample Student Records Information.
![Student Records](https://github.com/user-attachments/assets/914c6d2a-d87e-43b9-b06e-cde92d67f59c)

    - Sample Graduation Records Information.
![Graduation records](https://github.com/user-attachments/assets/73c8cfc3-deb2-4657-a2f5-ee75d2868d7e)
      
### Data Pipeline Design
 - Designed using draw.io to anlayse data processing stages.

![ETL](https://github.com/user-attachments/assets/d95b91b5-3d91-4169-8fba-9cd15b5aea17)
   
### AWS Services
 - AWS Services:
    - Amazon S3 for storage
    - AWS GlueData Brew for Cleaning and Structuring.
    - AWS Glue for Data Pipleline.

### Data Cleaning and Structuring
 - It includes operations such as
    - Checking invalid values in data set such as null rows.
    - Renaming of coloum names.
    - Change of Data Type for columns.
    - Change of Schema (Addition of Coloumn).
    - Creation and publishing of recipe.
  
![Data Transformation](https://github.com/user-attachments/assets/db441eb5-0266-48f6-911c-3c06a8b1f9c6)

### Data Pipeline Implementation:
 - Implemented using AWS Glue for ETL processes.
 - Transformation operations included schema changes, aggregation, and union operations.
   
![Data Pipeline](https://github.com/user-attachments/assets/c5c54041-9b76-4cb8-aac0-682901128319)

### Outcome
 - Figure shows the determination of metrics as deduced from ETL Glue.
   
![Outcome](https://github.com/user-attachments/assets/ef50dbd0-f11f-42d4-9a3e-7052bb8347e6)

### Insights and Findings
 - Student Graduation Rate (SGR) for 2023:
    - The graduation rate for the year 2023 is 66.67%.
    - This indicates that approximately two-thirds of the students enrolled in the relevant programs at UCW successfully graduated in 2023.
    - This rate reflects a decrease when compared to the previous year (2022).
      
 - Student Graduation Rate (SGR) for 2024:
    - The graduation rate for the year 2024 is 69.70%.
    - This shows a slight improvement over the 2023 graduation rate, suggesting positive changes in student performance or institutional effectiveness.
    - However, it still falls short of the graduation rate observed in 2022.

 - Trend Analysis:
    - There is a notable fluctuation in the graduation rates over the three years:
    - 2022: 73.53%
    - 2023: 66.67% (a decrease from 2022)
    - 2024: 69.70% (an increase from 2023 but still lower than 2022)
    - This trend highlights potential areas of concern in student retention or program effectiveness that UCW may need to address.

### Conclusion
 - The project effectively uses AWS Glue DataBrew for data cleaning and transformation, and the ETL pipeline is successfully executed to calculate the student graduation rate.
 - The entire workflow, from data preparation to final output generation, is well-organized with clear steps for extracting, transforming, and loading data into an S3 bucket.
 - The project aims to provide insights into university graduation rates by using a systematic data processing approach, and the documented pipeline reflects a comprehensive methodology to achieve the objective.
