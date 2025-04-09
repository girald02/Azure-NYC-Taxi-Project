# 🚖 Azure NYC Taxi Project – End-to-End Data Engineering Pipeline

An end-to-end modern data engineering project built on Microsoft Azure, using real-world NYC Taxi data as the source. 

This project follows the **Medallion Architecture** (Bronze → Silver → Gold) and demonstrates ingestion, transformation, and reporting using Azure-native tools.

---

## 🏗️ Architecture Overview

![Azure NYC Taxi Project Architecture](https://raw.githubusercontent.com/girald02/Azure-NYC-Taxi-Project/refs/heads/main/img_journey/Azure-NYC-Taxi-Project.jpg)


---

## 📊 Data Source

- **Official NYC Taxi Trip Record Data**  
  🔗 [NYC TLC Data Portal](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

- **Static Sample File**  
  📦 [green_tripdata_2023-01.parquet](https://d37ci6vzurychx.cloudfront.net/trip-data/green_tripdata_2023-01.parquet)

---

## 🧩 Tech Stack

| Tool                     | Purpose                                    |
|--------------------------|--------------------------------------------|
| Azure Data Factory       | Ingest raw files from HTTP dynamically     |
| Azure Data Lake Gen2     | Store data in Bronze, Silver, and Gold     |
| Azure Databricks         | Transform data using PySpark               |
| Delta Lake               | Time travel & version-controlled tables    |
| Power BI                 | Visualize the final data                   |
| Microsoft Entra ID (AAD) | Secure access between services             |

---

## ✅ Project Phases

### 🚀 Phase 1: Ingestion with Azure Data Factory (Bronze Layer)

- Built dynamic pipelines to pull monthly data from a public HTTP endpoint.
- Implemented `foreach` activity with parameterization for scalable ingestion.
- Used conditional logic (`if` expressions) to manage file handling dynamically.
- Stored the ingested raw Parquet files in Azure Data Lake’s **Bronze** layer.

---

### ⚙️ Phase 2: Transformation with Azure Databricks (Silver Layer)

- Connected Databricks securely to Azure Data Lake using **App Registration**.
- Transformed and enriched data using PySpark.
- Implemented recursive reading to automatically detect all subfolders/files.
- Stored clean data into the **Silver** layer for further analytics.

---

### ⚙️ Phase 3: Delta Lake – Gold Layer

- Converted Silver data to Delta format with versioning and schema enforcement.
- Created **external Delta tables** to allow querying with Spark SQL.
- Implemented **Time Travel** capabilities for historical data tracking.

---

### 📊 Phase 4: Business Intelligence with Power BI

- Connected Power BI to Databricks using Azure Marketplace connectors.
- Generated access token via Developer Settings in Databricks.
- Built and published dashboards on the Gold Layer data to visualize key metrics.

---

## 🔐 Security & Access Control

- Used **Microsoft Entra ID** (Azure Active Directory) for secure access.
- Registered an **Application (App Registration)** for Databricks to access Data Lake.
- Assigned roles via IAM (e.g., Storage Blob Data Contributor).
- Authenticated using OAuth with client ID, secret, and tenant ID credentials.

---

## 🙌 Acknowledgments

> 🎓 **Special thanks to [Ansh Lamba](https://github.com/anshlambagit/NYC-TAXI-DE-Project)** for the detailed tutorial that inspired and guided this project. Highly recommend his content for learning Azure data engineering!

## 📌 Key Features Implemented

- ✅ Parameterized pipeline ingestion in ADF  
- ✅ Scalable architecture using Medallion layering  
- ✅ PySpark transformations in Azure Databricks  
- ✅ Delta Lake storage with versioning & time travel  
- ✅ Secure OAuth authentication via Entra ID  
- ✅ Power BI dashboard integrated with Gold Layer

  

## 📎 Useful Links

- [NYC Trip Data Portal](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)  
- [Reference Tutorial by Ansh Lamba](https://www.youtube.com/watch?v=LQY2fvEv4cM)  

---

## 🤝 Let’s Connect!

I’m always open to feedback, collaboration, or even just talking data!  
Feel free to open issues or connect with me on [LinkedIn](https://www.linkedin.com/in/girald-bacongan-988144174/).
