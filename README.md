# 🚀 Azure End-to-End ETL Data Engineering Projects

A collection of **production-ready ETL pipelines** built with **Azure Data Factory**
covering two complete end-to-end data engineering workflows using
**MySQL** and **PostgreSQL** as sources, following **Medallion Architecture**.

---

## 📁 Projects Included

| Project | Source | Destination | Layers |
|---------|--------|-------------|--------|
| Project 1 | MySQL | Azure SQL Database | Bronze → Silver → Gold |
| Project 2 | PostgreSQL | Azure SQL Database | Bronze → Silver → Gold |

---

# 🗂️ PROJECT 1 — MySQL to Azure SQL Database

## 🏗️ Architecture Flow
---

## 📌 Pipeline 1 — MySQL to ADLS Gen2 (Ingestion)

| Property             | Value                        |
|----------------------|------------------------------|
| **Source**           | MySQL Database               |
| **Sink**             | Azure Data Lake Storage Gen2 |
| **Region**           | East Asia                    |
| **Status**           | ✅ Succeeded                 |
| **Rows Read**        | 100                          |
| **Rows Written**     | 100                          |
| **Data Read**        | 19 KB                        |
| **Data Written**     | 8.365 KB                     |
| **Copy Duration**    | 16 seconds                   |
| **Throughput**       | 6.333 KB/s                   |
| **Parallel Copies**  | 1                            |
| **Start Time**       | 4/28/2026, 4:27:09 PM        |

### 🖼️ Pipeline 1 Screenshot
![MySQL to ADLS Gen2](./screenshots/MySQL_ADLS_Silver.jpg)

---

## 📌 Pipeline 2 — ADF Mapping Data Flow (Transformation)

**Pipeline:** `Mysql_Silver_Gold` → `Data flow1`
**Data Flow Status:** ✅ Success
**Cluster Startup Time:** 4m 13s
**Number of Transformations:** 5

### 🔁 Data Flow Steps
### ⚙️ Transformation Details

| Step                 | Type            | Purpose                             |
|----------------------|-----------------|-------------------------------------|
| `sourceSilverMySQL`  | Source          | Read data from ADLS Gen2 Silver Layer |
| `DateColumnFormat`   | Derived Column  | Standardize date formats            |
| `removeDecimal`      | Derived Column  | Strip unwanted decimal values       |
| `PurchaseColumn`     | Derived Column  | Apply purchase business logic       |
| `sinkMysqlSQLDB`     | Sink            | Write cleansed data to SQL Database |

### 🖼️ Pipeline 2 Screenshot
![MySQL Silver Gold Data Flow](./screenshots/MySQL_ADLS_Silver_Transform_ADLSGold.jpg)

---

## 📌 Pipeline 3 — ADLS Gen2 to Azure SQL Database (Final Load)

| Property              | Value                        |
|-----------------------|------------------------------|
| **Source**            | Azure Data Lake Storage Gen2 |
| **Sink**              | Azure SQL Database           |
| **Region**            | East Asia                    |
| **Status**            | ✅ Succeeded                 |
| **Files Read**        | 1                            |
| **Rows Read**         | 100                          |
| **Rows Written**      | 100                          |
| **Data Read**         | 10.938 KB                    |
| **Data Written**      | 21.8 KB                      |
| **Copy Duration**     | 12 seconds                   |
| **Throughput**        | 3.646 KB/s                   |
| **DIUs Used**         | 4                            |
| **Start Time**        | 4/28/2026, 4:36:23 PM        |

### 🖼️ Pipeline 3 Screenshot
![ADLS Gen2 to Azure SQL](./screenshots/MySQL_ADLSGold_AzureSQL.jpg)

---

## 🏆 Project 1 — Pipeline Summary

| Pipeline | Source        | Sink                 | Rows | Duration | Status |
|----------|--------------|----------------------|------|----------|--------|
| 1        | MySQL         | ADLS Gen2 (Bronze)   | 100  | 16 sec   | ✅     |
| 2        | ADLS Gen2     | Data Flow Transform  | 100  | 4m 13s   | ✅     |
| 3        | ADLS Gen2     | Azure SQL Database   | 100  | 12 sec   | ✅     |

---
---

# 🗂️ PROJECT 2 — PostgreSQL to Azure SQL Database

## 🏗️ Architecture Flow
---

## 📌 Pipeline 1 — PostgreSQL to ADLS Gen2 (Ingestion)

| Property              | Value                          |
|-----------------------|--------------------------------|
| **Source**            | PostgreSQL                     |
| **Sink**              | Azure Data Lake Storage Gen2   |
| **Region**            | East Asia                      |
| **Status**            | ✅ Succeeded                   |
| **Rows Read**         | 100                            |
| **Rows Written**      | 100                            |
| **Data Read**         | 19.062 KB                      |
| **Data Written**      | 16.328 KB                      |
| **Files Written**     | 1                              |
| **Copy Duration**     | 14 seconds                     |
| **Throughput**        | 6.354 KB/s                     |
| **Parallel Copies**   | 1                              |
| **Start Time**        | 4/28/2026, 12:34:17 PM         |

### 🖼️ Pipeline 1 Screenshot
![PostgreSQL to ADLS Gen2](./screenshots/Postgre_ADLS.jpg)

---

## 📌 Pipeline 2 — Postgre_SilverLake_GoldLake (Data Flow Transformation)

**Pipeline:** `Postgre_SilverLake_GoldLake`
**Data Flow Status:** ✅ Success
**Cluster Startup Time:** 2m 26s
**Number of Transformations:** 4

### 🔁 Data Flow Steps
### ⚙️ Transformation Details

| Step               | Type            | Purpose                                    |
|--------------------|-----------------|--------------------------------------------|
| `sourceSilverLake` | Source          | Read data from ADLS Gen2 Silver Layer      |
| `EditDateColumns`  | Derived Column  | Standardize date formats for analytics     |
| `PurchaseColumn`   | Derived Column  | Apply business rules on purchase columns   |
| `sinkToGold`       | Sink            | Load clean data to Gold Layer              |

### 🖼️ Pipeline 2 Screenshot
![Postgre SilverLake GoldLake](./screenshots/Postgre_SilverLake_GoldLake.jpg)

---

## 📌 Pipeline 3 — ADLS Gen2 Gold to Azure SQL Database (Final Load)

| Property              | Value                        |
|-----------------------|------------------------------|
| **Source**            | Azure Data Lake Storage Gen2 |
| **Sink**              | Azure SQL Database           |
| **Region**            | East Asia                    |
| **Status**            | ✅ Succeeded                 |
| **Files Read**        | 1                            |
| **Rows Read**         | 100                          |
| **Rows Written**      | 100                          |
| **Data Read**         | 11.74 KB                     |
| **Data Written**      | 21.862 KB                    |
| **Copy Duration**     | 14 seconds                   |
| **Throughput**        | 2.935 KB/s                   |
| **DIUs Used**         | 4                            |
| **Start Time**        | 4/28/2026, 4:24:07 PM        |

### 🖼️ Pipeline 3 Screenshot
![PG Gold to Azure SQL](./screenshots/PGGold_AzureSQL.jpg)

---

## 🏆 Project 2 — Pipeline Summary

| Pipeline | Source              | Sink                 | Rows | Duration | Status |
|----------|--------------------|-----------------------|------|----------|--------|
| 1        | PostgreSQL          | ADLS Gen2 (Bronze)   | 100  | 14 sec   | ✅     |
| 2        | ADLS Gen2 (Silver)  | ADLS Gen2 (Gold)     | 100  | 2m 26s   | ✅     |
| 3        | ADLS Gen2 (Gold)    | Azure SQL Database   | 100  | 14 sec   | ✅     |

---
---

# 🛠️ Tech Stack (Both Projects)

- **Azure Data Factory** — Pipeline orchestration & monitoring
- **MySQL** — Relational source (Project 1)
- **PostgreSQL** — Relational source (Project 2)
- **Azure Data Lake Storage Gen2** — Bronze, Silver & Gold layers
- **ADF Mapping Data Flow** — Visual ETL transformation engine
- **Azure SQL Database** — Gold layer destination (Both Projects)
- **Azure Copy Activity** — Efficient data movement
- **Medallion Architecture** — Bronze → Silver → Gold pattern

---

# 📊 What This Demonstrates

- ✅ End-to-end **cloud data pipelines** on Azure
- ✅ **Medallion Architecture** (Bronze → Silver → Gold)
- ✅ **Multi-source ingestion** — MySQL & PostgreSQL
- ✅ **Data cleansing & transformation** using ADF Data Flows
- ✅ **Date formatting & business logic** application
- ✅ Real-world **pipeline execution metrics**
- ✅ Zero data loss — 100 rows in = 100 rows out

---

# 📁 Repository Structure
# 👨‍💻 Author

**Vishal Kumar Gatla**
Data Engineer | Azure Data Factory | MySQL | PostgreSQL | Medallion Architecture
