# 🏅 Tokyo Olympics Azure Data Engineering Project

## 📌 Project Overview
This project demonstrates an **end-to-end Azure Data Engineering pipeline** built using the **Tokyo Olympics dataset**.  
The objective of this project was to design and implement a modern cloud-based data pipeline that ingests raw data, transforms it using distributed processing, performs analytical querying, and exposes the final curated outputs to a reporting layer.

This project focuses primarily on **data engineering concepts**, including:
- Data ingestion
- Cloud storage architecture
- Data transformation
- Data lake integration
- Analytical querying
- Reporting layer integration

---

## 🚀 Tech Stack

- **Azure Data Factory (ADF)** – Data ingestion orchestration
- **Azure Data Lake Storage Gen2 (ADLS Gen2)** – Raw and transformed data storage
- **Azure Databricks** – Data transformation using PySpark
- **Azure Synapse Analytics** – SQL-based analytical querying
- **Power BI** – Reporting/dashboard layer
- **GitHub** – Version control and project showcase

---

## 🏗️ Architecture

![Project Architecture](images/Architecture.png)

---

## 🔄 Project Workflow

### 1. Data Source
The Tokyo Olympics dataset was collected from Kaggle and stored in the GitHub repository for ingestion.

### 2. Data Ingestion using Azure Data Factory
- Created an **Azure Data Factory pipeline**
- Used **HTTP linked service** to fetch raw CSV files from GitHub
- Ingested the files sequentially into **Azure Data Lake Storage Gen2**
- Stored the files inside the **`raw-data`** container

### 3. Data Storage using ADLS Gen2
Created a storage account with two containers:
- **`raw-data`** → stores raw ingested files
- **`transformed-data`** → stores cleaned/transformed output files

### 4. Data Transformation using Azure Databricks
- Created and configured an **Azure Databricks workspace**
- Connected Databricks with ADLS Gen2 using **App Registration**
- Used **PySpark** to:
  - Read raw files from ADLS
  - Apply transformations and standardization
  - Write transformed files back into the **`transformed-data`** container

### 5. Data Querying using Azure Synapse Analytics
- Created an **Azure Synapse workspace**
- Built external tables over transformed data stored in ADLS
- Queried the transformed datasets using **Synapse SQL**
- Generated final analytical outputs for reporting

### 6. Reporting Layer using Power BI
- Connected **Power BI** to **Azure Synapse Analytics**
- Imported curated analytical query outputs
- Built a **lightweight one-page reporting dashboard**
- Dashboard was intentionally kept simple, as the primary focus of this project is **data engineering**, not BI storytelling

  ![Dashboard](Images/Dashboard)

---

## 📂 Dataset Used

The project uses **5 Tokyo Olympics CSV datasets**:

- `Athletes.csv`
- `Coaches.csv`
- `EntriesGender.csv`
- `Medals.csv`
- `Teams.csv`

---

## 📁 Project Folder Structure

```bash
Tokyo-Olympics-Azure-Data-Engineering-Project/
│
├── data/
│   ├── Athletes.csv
│   ├── Coaches.csv
│   ├── EntriesGender.csv
│   ├── Medals.csv
│   └── Teams.csv
│
├── databricks/
│   └── Spark Code.ipynb
│
├── sql/
│   └── synapse_script.sql
│
├── images/
│   ├── architecture.png
│   └── dashboard.png
│
├── README.md

