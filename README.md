**azure-data-factory-mysql-adls-gen2-pipeline**

# 🚀 MySQL to Azure Data Lake Storage Gen2 — ADF ETL Pipeline

A production-ready data engineering pipeline built with **Azure Data Factory**
that extracts data from **MySQL** and loads it into **Azure Data Lake Storage Gen2**
with automated orchestration and monitoring.

---

## 📌 Project Overview

This pipeline demonstrates a complete **ELT/ETL workflow** using cloud-native
Azure services — from relational database extraction to scalable data lake storage,
ready for downstream analytics.

---

## ⚙️ Pipeline Details

| Property             | Value                        |
|----------------------|------------------------------|
| **Source**           | MySQL Database               |
| **Sink**             | Azure Data Lake Storage Gen2 |
| **Region**           | East Asia                    |
| **Status**           | ✅ Succeeded                 |
| **Rows Transferred** | 100 rows                     |
| **Data Read**        | 19 KB                        |
| **Data Written**     | 8.365 KB                     |
| **Copy Duration**    | 15 seconds                   |
| **Throughput**       | 3.167 KB/s                   |
| **Parallel Copies**  | 1                            |

---

## 🛠️ Tech Stack

- **Azure Data Factory** — Pipeline orchestration & monitoring
- **MySQL** — Relational source database
- **Azure Data Lake Storage Gen2** — Scalable cloud storage
- **Azure Copy Activity** — Efficient data movement

---

## 🏗️ Architecture
<img width="1501" height="883" alt="image" src="https://github.com/user-attachments/assets/d440fba7-28db-4074-9d44-8bba5e5b28bf" />

# 🔄 MySQL Silver Layer → SQL DB — Data Transformation Pipeline (Azure Data Flow)

A production-grade **data transformation pipeline** built with **Azure Data Factory Mapping Data Flow**
that cleanses, formats, and loads data from a **MySQL Silver Layer** into **SQL Database**
through a series of structured transformation steps.

---

## 📌 Project Overview

This pipeline showcases a real-world **Silver → Gold layer transformation** using
Azure Data Flow with multiple business logic transformations applied before
loading into the target SQL Database — a core concept in **Medallion Architecture**.

---

## 🔁 Pipeline Flow

<img width="1532" height="260" alt="image" src="https://github.com/user-attachments/assets/dee05077-bc4f-444c-827f-b3118acaa0cf" />


# 🔄 MySQL Silver Layer → SQL DB — Data Transformation Pipeline (Azure Data Flow)

A production-grade **data transformation pipeline** built with **Azure Data Factory Mapping Data Flow**
that cleanses, formats, and loads data from a **MySQL Silver Layer** into **SQL Database**
through a series of structured transformation steps.

---

## 📌 Project Overview

This pipeline showcases a real-world **Silver → Gold layer transformation** using
Azure Data Flow with multiple business logic transformations applied before
loading into the target SQL Database — a core concept in **Medallion Architecture**.

---

## 🔁 Pipeline Flow


<img width="1532" height="260" alt="image" src="https://github.com/user-attachments/assets/f733711c-9e38-4319-ba19-6ba081b6efd9" />


[Pipeline 1 - Ingestion]
MySQL (Source)
     │  19KB | 100 rows | 15 sec
     ▼
Azure Data Lake Storage Gen2 (East Asia)  ✅

[Pipeline 2 - Transformation]
ADLS Gen2 (Silver Layer)
     │
     ▼
DateColumnFormat → removeDecimal → PurchaseColumn
     │
     ▼
Transformed Data  ✅

[Pipeline 3 - Final Load]
ADLS Gen2 (East Asia)
     │  10.938KB read | 21.8KB written | 12 sec
     ▼
Azure SQL Database (East Asia)  ✅


<img width="1439" height="870" alt="image" src="https://github.com/user-attachments/assets/0975a521-2bcc-4dc5-a196-e78c8a6de1bd" />










