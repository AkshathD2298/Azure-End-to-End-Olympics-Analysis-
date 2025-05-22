# Olympics Data Analytics Pipeline using Azure

This project demonstrates a complete end-to-end **modern data pipeline** using Microsoft Azure. It fetches **Olympics data** from a public HTTP source (GitHub), stages it in **Azure Storage Accounts**, transforms it with **Azure Databricks**, stores clean data in **Azure Data Lake Gen2**, and finally queries it using **Azure Synapse Analytics** and visualizes the insights with **Power BI**.

---

##  Project Overview

- **Data Source**: Olympics dataset from [Kaggle](https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results)
- **Data Hosting**: Dataset uploaded to [GitHub][AkshathD2298] for HTTP-based access
- **Storage**: Azure Blob Storage & Azure Data Lake Storage Gen2
- **Processing**: Azure Databricks for data transformation & cleaning
- **Querying**: Azure Synapse Analytics for large-scale querying
- **Visualization**: Power BI for interactive dashboards

---

## 📁 Architecture Diagram

```plaintext
GitHub (Olympics CSV) 
        ↓
  Azure Storage Account (Raw Data)
        ↓
Azure Data Lake Gen2 (Raw Zone)
        ↓
    Azure Databricks
        ↓
Azure Data Lake Gen2 (Clean Zone)
        ↓
Azure Synapse Analytics
        ↓
        Power BI
```


##  Tech Stack

| Azure Service / Tool        | Purpose                                                                 |
|-----------------------------|-------------------------------------------------------------------------|
| **GitHub (HTTP URL)**       | Hosting Olympics CSV file for HTTP-based ingestion                      |
| **Azure Blob Storage**      | Initial staging of raw data                                             |
| **Azure Data Lake Gen2**    | Raw + Processed data storage                                            |
| **Azure Databricks**        | Data transformation, cleansing                                          |
| **Azure Synapse Analytics** | Analytics	SQL querying on clean data                                    |
| **Azure Data Factory** *    | Orchestrating data movement and pipeline automation                     |
| **Power BI**                | Dashboard & data visualization                                          |
| **Python / PySpark**        | Used within Databricks for data wrangling and transformation            |


##  Data Pipeline Flow

Data Upload: The original Olympics CSV file is hosted on GitHub for HTTP access.

Ingestion: Azure Data Factory (or Azure Function/Logic App) fetches the CSV and loads it into an Azure Storage account.

Raw Zone: Data is moved into the raw zone of Azure Data Lake Gen2.

Transformation: Azure Databricks reads the raw data, performs cleaning (nulls, duplicates, column formatting), and writes to the clean zone of the data lake.

Querying: Azure Synapse Analytics connects to the clean data zone for querying.

Visualization: Power BI imports data from Synapse to create visual analytics and dashboards.



