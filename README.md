# Fintech_Data_Migration


  <br>
  <br>
   

## PROJECT OVERVIEW

The project automates the process of fetching news articles related to Tesla from the News API, processing this data, and storing it in Google Cloud Storage (GCS) as a Parquet file. This file is later moved to a Snowflake data warehouse for analysis. The project uses Airflow for orchestration, ensuring the data ingestion and processing occur periodically and smoothly.

 <br>




### PROJECT EXPLANATION :-  


#### Data Fetching: 
The pipeline retrieves recent news articles related to Tesla using the News API. Each article’s data, including author, title, source, timestamp, and content, is processed and stored in a DataFrame.

#### Data Processing and Storage in GCS:

After processing, the data is saved locally as a Parquet file.
The file is then uploaded to a specified location in a Google Cloud Storage (GCS) bucket.

#### Data Loading to Snowflake:

In Snowflake, a destination table is created if it doesn’t already exist.
The Parquet file from the GCS bucket is copied into this destination table for analysis.

#### Airflow Orchestration:
Airflow manages and schedules the pipeline, triggering data fetching, processing, storage, and loading operations daily.

  
  
  
   
   
      


     

  



















<br>
<br>
<br>

## ARCHITECTURE DIAGRAM :-

![Project Architecture](FintechData_migration.png)  




 Python, Azure SQL Database, SQL, Azure Synapse, ADLS, PySpark, Delta Tables





<br>
<br>
<br>

## TECHNOLOGY USED :-

<h3> Azure SQL Database:</h3>

Orchestrates the entire workflow by defining tasks that automate fetching, processing, saving, and uploading data.

<h3>Azure Synapse:</h3>

Used for scripting the logic for data fetching, processing, and file handling.

<h3> ADLS:</h3>

Provides news data based on search queries. It offers access to various news articles, including their metadata, such as title, author, and content.

<h3> PySpark:</h3>

A Python library used to handle the structured data (articles) in a DataFrame, process it, and save it to disk in a columnar format (Parquet).

<h3>Google Cloud Storage (GCS):</h3>

A cloud storage service where the processed Parquet files are stored temporarily before being ingested into Snowflake.

<h3> Delta Tables:</h3>

Data warehouse that will eventually store and analyze the news data once it's transferred from GCS.











<br>
<br>
<br>



## Project Files  :-

* <h3>Pyspark Notebooks:

  ####  Bronze to Silver Transformation :
  [Notebook-1](BronzeToSilverDataProcess.ipynb) 
* Handles the ingestion and transformation of raw datasets.
   </br>
   
  ####  Silver to Gold Transformation :
  [Notebook-2](SilverToGoldDataProcess.ipynb) 
* Converts structured data into analytical tables.

    #### BRONZE:- Raw data
    #### SILVER:- Transform data
    #### GOLD:- Final Aggregated data
 
 </br>
 </br>
 
* <h2>SQL Scripts :</h2>

   ####  Define the source tables and schema for various datasets: :
 * [ACCOUNTS-TABLE](Accounts.sql) 
 * [CUSTOMERS-TABLE](Customers.sql) 
 * [LOANS-TABLE](Loans.sql) 
 * [PAYMENTS-TABLE](Payments.sql) 
 * [TRANSACTIONS-TABLE](Transactions.sql)


  </br>
  </br>

  











